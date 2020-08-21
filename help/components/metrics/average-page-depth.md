---
title: Profondeur moyenne de page
description: Le nombre moyen de pages dans lesquelles se trouve la dimension.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 59%

---


# Profondeur moyenne de page

La mesure &quot;Profondeur moyenne de page&quot; indique à quelle distance se trouve l’élément de dimension au cours d’une visite donnée. Par exemple, votre page d’accueil affiche généralement une profondeur moyenne de page inférieure à celle de votre page de confirmation d’achat, qui se trouve généralement à un stade plus avancé de la visite. Cette mesure s’avère utile lorsque vous souhaitez comprendre le nombre de pages d’un élément de dimension donné qui se trouvent en moyenne. Vous pouvez utiliser ces informations afin d’optimiser certaines pages pour les nouveaux visiteurs si la profondeur moyenne de la page est faible.

>[CONSEIL] Utilisez cette mesure avec une autre mesure ([Visites](visits.md), par exemple) pour obtenir de meilleures informations. Si vous utilisez cette mesure seule, vous obtenez des éléments de dimension contenant des profondeurs de page irrégulières, ce qui n’a généralement pas de valeur.

## Méthode de calcul de cette mesure

La profondeur de page de la première page d’une visite correspond à `0`. La profondeur de page de la page suivante correspond à 1 et augmente chaque page vue jusqu’à la fin de la visite. Cette mesure augmente uniquement avec les appels ([`t()`](/help/implement/vars/functions/t-method.md)) de pages vues et non avec les appels ([`tl()`](/help/implement/vars/functions/tl-method.md)) de suivi de liens.

Pour un élément de dimension donné, ajoutez toutes les profondeurs de page de cet élément de dimension et divisez-le par des visites. Le nombre obtenu correspond à la profondeur moyenne de page, arrondie au nombre entier le plus proche. Dimension items with an average page depth of `0` means it was frequently on the first page of the visit.

Prenons la visite suivante pour exemple :

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

If we wanted average page depth for the dimension item `Page2`, it would be calculated as follows:

```text
If 'Count repeat instances' is enabled:
(1 + 2 + 5) / 3 = 2.67, rounded up to 3

If 'Count repeat instances' is disabled:
(1 + 4) / 2 = 2.5, rounded up to 3
```

>[!TIP]
>
>Si vous souhaitez afficher la profondeur moyenne de page avec une décimale, créez une mesure calculée à l’aide de cette mesure comme seul élément de la formule. Augmentez le nombre de décimales de la mesure calculée pour atteindre le nombre de décimales souhaité.

## Pourcentages supérieurs à 100 %

Cette mesure contient souvent des pourcentages supérieurs à 100 %. Le dénominateur correspond à la profondeur de page moyenne de la dimension entière et le numérateur à la profondeur de page moyenne de l’élément de dimension. Si la profondeur de page moyenne de la dimension entière est inférieure à la profondeur de page moyenne d’un élément de dimension donné, vous verrez des pourcentages supérieurs à 100 %. Le tri des rapports de classement en fonction de cette mesure affiche les valeurs d’anomalie de profondeur moyenne de page, qui sont généralement inutiles. Adobe recommande de trier selon une autre mesure, telle que [Visites](visits.md), dans les rapports de classement.