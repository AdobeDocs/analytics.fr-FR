---
title: Totaux des mesures calculées
description: Découvrez comment les totaux des mesures calculées diffèrent dans les outils Analytics.
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Totaux des mesures calculées

L’affichage des totaux des mesures calculées diffère entre [!DNL Reports & Analytics] et [!DNL Analysis Workspace]. Cette section explique les différences.

## Totaux des mesures calculées dans [!DNL Reports & Analytics]

Lorsque vous affichez des rapports dans [!DNL Reports & Analytics], les mesures calculées affichent toujours `n/a` sous le total. Puisque toutes les mesures calculées sont définies par l’utilisateur, il existe de nombreuses situations dans lesquelles ce total n’est pas pertinent. Examinez l’exemple suivant :

Votre organisation a créé la mesure calculée `orders` / `visits` pour déterminer le pourcentage de visites au cours desquelles quelque chose a été acheté sur votre site. Si vous avez intégré cette mesure dans un rapport de produits, plusieurs produits sont attribués à une seule commande. Plusieurs produits sont également attribués à une seule visite. Si un total des mesures calculées a été inclus dans ce rapport, les questions suivantes se posent :

| Question | Réponse |
|---|---|
| Est-ce que la somme des éléments de ligne est logique ? | Non, car plusieurs produits peuvent être inclus dans une seule commande et dans une seule visite. Si les éléments de ligne étaient agrégés, le total des commandes et le total des visites ne correspondrait pas au total réel des commandes et des visites. |
| Est-ce qu’il est logique de prendre le total des commandes et des visites ? | Non, car le total ne correspond pas à la somme des éléments de ligne individuels. En outre, le total des commandes et le total des visites sont des mesures calculées séparément. |

Comme il n’existe aucune méthode logique et concrète pour déterminer si une mesure calculée est logique dans les rapports, le total de la mesure est complètement omis. Si vous souhaitez obtenir un total général, vous pouvez effectuer l’une des opérations suivantes :

* Créez une mesure calculée qui inclut les versions totales des mesures que vous souhaitez inclure.
* Créez un rapport Extraction de données, qui peut être planifié.
* Créez une requête de données dans [!DNL ReportBuilder].
* Utilisez [!DNL Analysis Workspace] (voir ci-dessous).

## Totaux des mesures calculées dans [!DNL Analysis Workspace]

Lorsque vous affichez des données dans Analysis Workspace, les totaux des mesures calculées s’affichent dans la plupart des cas. Dans certains cas, il n’est pas possible de fournir un total, par exemple lorsque les lignes du rapport présentent un format mixte (décimal et devise, par exemple).

Lorsque des totaux sont affichés, ils sont souvent calculés côté serveur, ce qui signifie que le total déduplique les mesures telles que les visites ou les visiteurs. Dans certaines circonstances, les mesures calculées sont générées côté client en additionnant les lignes du tableau, ce qui signifie que le total ne déduplique pas les mesures, comme les visites ou les visiteurs. Cela se produit dans les circonstances suivantes :

* Lorsque des [lignes statiques](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) sont utilisées dans des tableaux à structure libre, l’option **[!UICONTROL Afficher comme somme des lignes actuelles]** (par défaut) est sélectionnée.
* Dans la [visualisation Anneau](/help/analyze/analysis-workspace/visualizations/donut.md), afin que la somme des nombres s’élève à 100 %.
