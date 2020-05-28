---
description: 'En savoir plus sur les '
title: Type de mesure et attribution
uuid: 64649698-df2a-42c3-bb31-938f766e1d1f
translation-type: tm+mt
source-git-commit: a5ab9f3c0a82a5a37a6507b697c641c66075b848
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 80%

---


# Type de mesure et attribution

Lorsque vous sélectionnez l’icône représentant un engrenage en regard d’une mesure, vous pouvez spécifier le type de mesure et le modèle d’attribution.

## Type de mesure

![](assets/cm_type_alloc.png)

| Type de mesure | Définition |
|---|---|
| Standard | Ces mesures sont les mêmes mesures que celles utilisées dans la création de rapports standard [!DNL Analytics]. Si une formule est composée d’une seule mesure standard, elle affiche des données identiques à sa contrepartie de mesure non calculée. Les mesures standard sont utiles pour créer des mesures calculées spécifiques à chaque ligne. Par exemple, [Commandes] / [Visites] utilise des commandes pour cette ligne spécifique et la divise par le nombre de visites correspondant à cette ligne spécifique. |
| Total | Utilisez le total correspondant à la période de création de rapports de chaque ligne. Si une formule est composée d’un nombre total de mesures unique, elle affiche le même nombre total sur chaque ligne. Le nombre total de mesures est utile pour la création de mesures calculées qui sont comparées au nombre total de données du site. Par exemple, [Commandes] / [Nombre total de visites] affiche la proportion des commandes par rapport à TOUTES les visites sur votre site, et non juste les visites sur la ligne spécifique objet. |

## Modèle d’attribution de colonnes

>[!IMPORTANT]
>
>En juillet 2018, [!DNL Analytics] a ajouté la nouvelle fonctionnalité [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html), qui a revu la manière dont les modèles d’attribution dans les mesures calculées sont évalués. Dans le cadre de cette modification, les mesures calculées qui n’utilisent pas un modèle d’attribution par défaut ont été migrées vers des nouveaux modèles d’attribution améliorés :
>
>* Pour obtenir la liste complète des modèles d’attribution qui ne sont pas par défaut et les intervalles de recherche en amont pris en charge, consultez la documentation d’[Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html).
>* Les modèles d’attribution « Dernière touche canal marketing » et « Première touche canal marketing » seront migrés vers les nouveaux modèles d’attribution « Dernière touche » et « Première touche », respectivement. (Remarque : les rapports « Canaux marketing » ne seront pas obsolètes, seuls les deux modèles d’attribution qui apparaissent dans les mesures calculées le seront.)
>* De plus, nous corrigerons la façon dont l’affectation linéaire est calculée. Pour les clients qui utilisent des mesures calculées avec des modèles d’attribution « linéaire », les rapports peuvent légèrement changer afin de tenir compte du nouveau modèle d’attribution corrigé. Cette modification des mesures calculées sera reflétée dans Analysis Workspace, Reports &amp; Analytics, l’API de création de rapports, Report Builder et Ad Hoc Analysis. For more information, see **How Linear Allocation works (as of July 19, 2018**, below.
>



## Fonctionnement de l’attribution linéaire (au 19 juillet 2018)

En juillet 2018, Adobe a modifié la manière de générer des rapports sur l’affectation linéaire pour les mesures calculées. Cette modification a un impact sur Analysis Workspace, sur l’Ad Hoc Analysis, sur les Reports &amp; Analytics, sur le Report Builder, sur Activity Map et sur les API de création de rapports. Ce changement a principalement un impact sur les eVars et les autres dimensions qui ont une persistance. Notez que ces modifications s’appliquent uniquement aux mesures calculées et n’affectent pas les autres rapports à l’aide d’une attribution linéaire (comme le rapport Pages dans les rapports et analyses). Les autres rapports utilisant l’affectation linéaire continueront d’appliquer la méthode existante d’affectation linéaire.

L’exemple suivant explique comment les mesures calculées avec l’affectation linéaire changeront dans les rapports :

|  | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 | Accès 6 | Accès 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| Données envoyées dans | PROMO A | - | PROMO A | PROMO B | - | PROMO C | $10 |
| eVar de dernière touche | PROMO A | PROMO A | PROMO A | PROMO B | PROMO B | PROMO C | $10 |
| eVar de première touche | PROMO A | PROMO A | PROMO A | PROMO A | PROMO A | PROMO A | $10 |
| Exemple de Prop | PROMO A | - | PROMO A | PROMO B | - | PROMO C | $10 |

Dans cet exemple, les valeurs A, B et C ont été envoyées dans une variable aux accès 1, 3, 4 et 6 avant la réalisation d’un achat de 10 $ à l’accès 7. Dans la deuxième ligne, ces valeurs persistent dans les accès sur une base de visite de dernière touche. La troisième ligne représente une persistance de visite de première touche. Enfin, la dernière ligne indique comment les données seraient enregistrées pour une Prop qui ne présente pas de persistance.

## Différences entre le fonctionnement de l’attribution linéaire dans les rapports et analyses et l’espace de travail

Il existe des différences dans le fonctionnement de l’attribution linéaire entre ces deux outils :

* Dans les rapports et analyses, l’attribution linéaire (traitée) est toujours basée sur les visites, tandis que dans Workspace, elle peut être basée sur les visites ou les visiteurs.
* Dans les rapports et analyses, si aucune valeur n’a été transmise lors du premier accès d’une visite, la valeur (initiale) persiste lors de la visite précédente. Ceci n’est PAS le cas dans Workspace (Attribution IQ). Si aucune valeur n’est transmise lors du premier accès d’une visite, &quot;Aucun&quot; est la valeur initiale.

## Fonctionnement de l&#39;attribution linéaire avant juillet 2018

Avant le 19 juillet 2018, l’attribution linéaire était calculée après que la persistance de première touche ou de dernière touche ait eu lieu. Cela signifiait que pour l’eVar de dernière touche ci-dessus, les 10 $ auraient été distribués comme suit : A = 10 * (3/6) = 5 $, B = 10 * (2/6) = 3,33 $, C = 10 * (1/6) = 1,67 $.

Pour l’eVar de première touche ci-dessus, les 10 $ auraient été entièrement attribués à A. Pour la Prop : A = 10 * (2/4) = 5 $, B = 10 * (1/4) = 2,50 $, et C = 10 * (1/4) = 2,50 $. Pour résumer l’affectation linéaire telle qu’elle fonctionnait auparavant :

| Valeurs | eVar de dernière touche actuelle | eVar de première touche actuelle | Prop actuelle |
|---|---|---|---|
| PROMO A | 5,00 $ | 10,00 $ | 5,00 $ |
| PROMO B | 3,33 $ | $0 | 2,50 $ |
| PROMO C | 1,67 $ | $0 | 2,50 $ |
| Total | 10,00 $ | 10,00 $ | 10,00 $ |

**Résumé du fonctionnement de l’affectation linéaire à partir du 19 juillet 2018**

À compter du 19 juillet, nous avons corrigé ce comportement dans les mesures calculées. Au lieu d’utiliser les valeurs qui ont persisté sur la base de la dernière ou de la première touche, [!DNL Analytics] utilise maintenant uniquement les valeurs qui ont été passées (première ligne en haut du tableau). En tant que tels, les paramètres d’affectation de dimension n’ont plus d’impact sur la manière dont l’affectation linéaire est calculée (autrement dit, les Props et les eVars sont traitées de la même manière), et les résultats reflètent ce qui a été passé à l’origine plutôt que les valeurs de première touche et de dernière touche qui peuvent avoir persisté. Ainsi, dans les trois cas, A = 10 * (2/4) = 5 $, B = 10 * (1/4) = 2,50 $ et C = 10 * (1/4) = 2,50 $.

| Valeurs | Nouvelle eVar de dernière touche | Nouvelle eVar de première touche | Nouvelle Prop |
|---|---|---|---|
| PROMO A | 5,00 $ | 5,00 $ | 5,00 $ |
| PROMO B | 2,50 $ | 2,50 $ | 2,50 $ |
| PROMO C | 2,50 $ | 2,50 $ | 2,50 $ |
| Total | 10,00 $ | 10,00 $ | 10,00 $ |

