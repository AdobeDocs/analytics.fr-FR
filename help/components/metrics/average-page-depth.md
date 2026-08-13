---
title: Profondeur moyenne de page
description: Le nombre moyen de pages dans lesquelles se trouve la dimension.
feature: Metrics
exl-id: 6625405a-bda5-4723-8d22-4bc5b7e44d4e
TQID: https://experienceleague.adobe.com/Pm2WxRPqn9M-7IdrFQ2Tkj9t-L8ug3nZGr6ncpZg7lg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 365
ht-degree: 55%

---

# Profondeur moyenne de page

La [mesure](overview.md) « Profondeur de page moyenne » indique jusqu’à quel point un élément de dimension s’étend sur une visite donnée, en moyenne. Par exemple, votre page d’accueil (qui est un élément de dimension pour la dimension Page ) affiche généralement une profondeur de page moyenne plus faible que votre page de confirmation d’achat, ce qui s’étend probablement plus loin lors d’une visite. Vous pouvez utiliser ces informations pour optimiser l’affichage de certaines pages pour les nouveaux visiteurs si la profondeur de la page est faible, en moyenne.

>[!TIP]
>
>Utilisez cette mesure avec une autre mesure, telle que [Visites](visits.md), pour obtenir de meilleurs informations. Si vous utilisez cette mesure seule, vous pouvez obtenir des éléments de dimension contenant des profondeurs de page anormales, ce qui n’est généralement pas un élément insight de valeur.

## Méthode de calcul de cette mesure

La profondeur de page de la première page d’une visite correspond à `0`. La profondeur de page de la page suivante correspond à 1 et augmente chaque page vue jusqu’à la fin de la visite. Cette mesure augmente uniquement avec les appels de page vue ([`t()`](/help/implement/vars/functions/t-method.md)), et non avec les appels de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)).

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

Cette mesure contient souvent des pourcentages supérieurs à 100 %. Le dénominateur est la profondeur de page moyenne de l’ensemble de la dimension, et le numérateur est la profondeur de page moyenne de l’élément de dimension.

Si la profondeur de page moyenne de l’ensemble de la dimension est inférieure à celle d’un élément de dimension donné, des pourcentages supérieurs à 100 % s’affichent. Le tri des rapports de classement en fonction de cette mesure affiche les valeurs d’anomalie de profondeur moyenne de page, qui sont généralement inutiles. Adobe recommande de trier selon une autre mesure, telle que [Visites](visits.md), dans les rapports de classement.
