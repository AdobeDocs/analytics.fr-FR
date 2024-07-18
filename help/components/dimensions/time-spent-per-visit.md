---
title: Durée de la visite (dimensions)
description: La durée totale de la visite.
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 91%

---

# Durée de la visite

*Cette page d’aide décrit le fonctionnement de la &quot;Durée de la visite&quot; en tant que [dimensions](overview.md) respectives. Pour plus d’informations, consultez la mesure [Durée de la visite](../metrics/time-spent-per-visit.md).*

Les dimensions « Durée de la visite » enregistrent le temps passé par un visiteur pendant l’intégralité de la visite. Elle utilise les étapes suivantes pour mesurer le calcul :

1. Examinez l’heure et la date du premier accès de la visite.
2. Comparez cet accès à l’horodatage du dernier accès de la visite.
3. Le temps écoulé entre ces deux accès contribue à la durée de consultation.

Ces dimensions sont utiles pour déterminer la durée d’interaction des visiteurs avec votre site en général.

>[!TIP]
>
>Lors d’une visite, au moins deux accès sont nécessaires pour mesurer la durée. Les visites composées d’un seul accès n’apparaissent pas dans cette dimension.

Cette dimension est basée sur les visites, ce qui signifie que la valeur s’applique à chaque accès lors de la visite et ne change pas. Comparez cette dimension à la [durée de consultation de la page](time-spent-on-page.md), qui est une dimension basée sur les accès.

Cette dimension est liée aux mesures [Durée moyenne de la visite du site](../metrics/average-time-on-site.md) et [Durée de la visite](../metrics/time-spent-per-visit.md).

## Renseignement de cette dimension avec des données

Ces dimensions sont prêtes à l’emploi pour toutes les implémentations. Si une suite de rapports contient des données, ces dimensions fonctionnent.

## Éléments de dimension

La durée de la visite comporte plusieurs dimensions :

* **Durée de la visite - regroupée** : la durée est regroupée. Les éléments de dimension sont compris entre `"Less than 1 minute"` et `"More than 15 hours"`. En règle générale, les visites ne durent pas plus de 12 heures. Toutefois, les visites peuvent dépasser 12 heures si vous utilisez des accès horodatés ou des sources de données.
* **Durée de la visite - granulaire** : chaque nombre de secondes est un élément de dimension unique. Cette dimension n’est pas disponible en Data Warehouse.

Consultez [Présentation de la durée de consultation](../metrics/time-spent.md) pour obtenir des informations plus générales sur la durée de consultation.
