---
title: Durée de la visite
description: Durée totale de la visite.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 11%

---


# Durée de la visite

*Cette page d’aide décrit le fonctionnement de la mesure &quot;Durée de la visite&quot; en tant que dimensions respectives. Pour plus d’informations, voir la mesure[Durée de la visite](../metrics/time-spent-per-visit.md).*

Les dimensions &quot;Temps passé par visite&quot; enregistrent la durée passée par un visiteur sur la totalité de la visite. Elle utilise les étapes suivantes pour mesurer le calcul :

1. Examinez l’horodatage du premier accès de la visite.
2. Comparez cet accès à l’horodatage du dernier accès de la visite.
3. La durée écoulée entre ces deux accès contribue au temps passé.

Ces dimensions sont utiles pour comprendre la durée d’interaction des visiteurs avec votre site en général.

>[!TIP]
>
>La durée de la visite nécessite au moins deux accès pour mesurer la durée. Les visites composées d’un seul accès n’apparaissent pas dans cette dimension.

Cette dimension est basée sur les visites, ce qui signifie que la valeur s’applique à chaque accès de la visite et ne change pas. Comparez cette dimension à la [durée de consultation de la page](time-spent-on-page.md), qui est une dimension basée sur les accès.

Cette dimension est liée aux mesures de temps [moyen passé sur le site](../metrics/average-time-on-site.md) et de [temps passé par visite](../metrics/time-spent-per-visit.md) .

## Renseigner cette dimension avec des données

Ces dimensions sont prêtes à l’emploi pour toutes les implémentations. Si une suite de rapports contient des données, ces dimensions fonctionnent.

## Valeurs de dimension

Il existe plusieurs dimensions pour le temps passé par visite :

* **Durée de la visite - cumulée**: La durée est cumulée. Les valeurs de dimension vont `"Less than 1 minute"` de à `"More than 15 hours"`. En règle générale, les visites ne durent pas plus de 12 heures ; toutefois, les visites peuvent dépasser 12 heures si vous utilisez des accès horodatés ou des sources de données.
* **Durée de la visite - granulaire**: Chaque nombre de secondes est une valeur de dimension unique. Cette dimension n’est pas disponible dans les rapports et Analytics ni dans le Data warehouse.

Voir Présentation [de la](../metrics/time-spent.md) durée de la visite pour obtenir des informations plus générales sur la durée de la visite.
