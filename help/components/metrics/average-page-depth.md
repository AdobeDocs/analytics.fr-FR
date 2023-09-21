---
title: Profondeur moyenne de page
description: Le nombre moyen de pages dans lesquelles se trouve la dimension.
feature: Metrics
exl-id: 6625405a-bda5-4723-8d22-4bc5b7e44d4e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 60%

---

# Profondeur moyenne de page

&quot;Profondeur moyenne de page&quot; [metric](overview.md) indique la distance moyenne d’un élément de dimension sur une visite donnée. Par exemple, votre page d’accueil (qui est un élément de dimension pour la dimension Page) affiche généralement une profondeur moyenne de page inférieure à celle de votre page de confirmation d’achat, ce qui s’étend probablement plus loin dans une visite. Vous pouvez utiliser ces informations pour optimiser certaines pages pour les nouveaux visiteurs si la profondeur moyenne de la page est faible.

>[!TIP]
>
>Utilisez cette mesure avec une autre mesure, telle que [Visites](visits.md), afin d’obtenir de meilleures informations. Si vous utilisez cette mesure seule, vous pouvez obtenir des éléments de dimension contenant des profondeurs de page anormales, ce qui n’est généralement pas une information utile.

## Méthode de calcul de cette mesure

La profondeur de page de la première page d’une visite correspond à `0`. La profondeur de page de la page suivante correspond à 1 et augmente chaque page vue jusqu’à la fin de la visite. Cette mesure augmente uniquement avec la page vue ([`t()`](/help/implement/vars/functions/t-method.md)) et non avec le suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)).

Pour un élément de dimension donné, ajoutez toutes les profondeurs de page de celui-ci et divisez-les par le nombre de visites. Le nombre obtenu correspond à la profondeur moyenne de page, arrondie au nombre entier le plus proche. Les éléments de dimension dotés d’une profondeur moyenne de page de `0` indiquent une présence fréquente sur la première page de la visite.

Prenons la visite suivante pour exemple :

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

Si nous voulions une profondeur moyenne de page pour l’élément de dimension `Page2`, elle serait calculée comme suit :

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

Cette mesure contient souvent des pourcentages supérieurs à 100 %. Le dénominateur correspond à la profondeur moyenne de page de l’ensemble de la dimension et le numérateur à celle de l’élément de dimension.

Si la profondeur moyenne de page de l’ensemble de la dimension est inférieure à celle d’un élément de dimension donné, les pourcentages sont supérieurs à 100 %. Le tri des rapports de classement en fonction de cette mesure affiche les valeurs d’anomalie de profondeur moyenne de page, qui sont généralement inutiles. Adobe recommande de trier selon une autre mesure, telle que [Visites](visits.md), dans les rapports de classement.
