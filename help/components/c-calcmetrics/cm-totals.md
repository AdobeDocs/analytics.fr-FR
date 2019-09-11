---
title: Totaux des mesures calculées
seo-title: Totaux des mesures calculées
description: Découvrez comment les totaux des mesures calculées diffèrent dans les outils Analytics
seo-description: Calcul des totaux des mesures calculées
translation-type: tm+mt
source-git-commit: 658925799c530b46ff7b56d5d0685af6d9fef1b8

---


# Totaux des mesures calculées

L'affichage des totaux des mesures calculées varie entre [!DNL Reports & Analytics] et [!DNL Analysis Workspace]. Cette section explique les différences.

## Totaux des mesures calculées dans [!DNL Reports & Analytics]

Lorsque vous affichez les rapports dans [!DNL Reports & Analytics]les mesures calculées, les mesures calculées s'affichent `n/a` toujours sous le total. Comme toutes les mesures calculées sont définies par l'utilisateur, il existe de nombreuses circonstances dans lesquelles ce total n'a aucun sens. Examinez l’exemple suivant :

Votre entreprise a créé la mesure `orders` calculée/ `visits` pour déterminer le pourcentage de visites ayant acheté un article sur votre site. Si vous avez apporté cette mesure dans un rapport de produits, plusieurs produits sont attribués à une seule commande. De plus, plusieurs produits sont attribués à une seule visite. Si le total des mesures calculées était inclus dans ce rapport, les questions suivantes se produisaient :

| Question | Réponse |
|---|---|
| La somme des éléments de ligne est-elle logique ? | Ce n'est pas le cas, car plusieurs produits peuvent être inclus dans une seule commande et plusieurs produits peuvent être inclus dans une seule visite. Si les lignes ont été agrégées, le total des commandes et le nombre total de visites ne correspondrait pas aux commandes totales et aux visites totales. |
| Le nombre total de commandes et de visites totales est-il logique ? | Ce n'est pas le cas, car le total ne correspond pas à la somme des éléments individuels. En outre, Total des commandes et Visites totales sont des mesures calculées séparément. |

Puisqu'il n'existe pas de méthode logique et concrète pour déterminer si une mesure calculée est logique dans les rapports, le total de la mesure est omis. Si vous souhaitez obtenir un total général, vous pouvez effectuer l'une des opérations suivantes :

* Créez une mesure calculée qui inclut le total des mesures que vous souhaitez inclure.
* Créez un rapport Extraction de données qui peut être planifié.
* Create a data request within [!DNL ReportBuilder].
* Utilisation [!DNL Analysis Workspace] (voir ci-dessous).

## Totaux des mesures calculées dans [!DNL Analysis Workspace]

Lorsque vous affichez les données dans Analysis Workspace, les totaux des mesures calculées sont affichés dans la plupart des cas. Dans certains cas, la fourniture d'un total n'est pas possible, par exemple lorsque les lignes du rapport sont de format mixte (par exemple, décimal et devise).

Lorsque les totaux sont affichés, ils sont souvent calculés côté serveur, ce qui signifie que le total déduplique les mesures comme les visites ou les visiteurs. Dans certains cas, les mesures calculées sont générées côté client en additionnant les lignes du tableau, ce qui signifie que le total ne déduplique pas les mesures comme les visites ou les visiteurs. Cela se produit :

* Lorsque [des lignes statiques](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) sont utilisées dans les tableaux à structure libre et que **[!UICONTROL l'option Afficher comme somme des lignes]** actives (par défaut) est sélectionnée.
* Dans la visualisation [des anneaux](/help/analyze/analysis-workspace/visualizations/donut.md), de sorte que les nombres atteignent jusqu'à 100 %.
