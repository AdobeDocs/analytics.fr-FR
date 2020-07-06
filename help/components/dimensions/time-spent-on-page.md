---
title: Durée de consultation de la page
description: Durée passée par un visiteur sur la page.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 13%

---


# Durée de consultation de la page

La dimension &quot;Durée de consultation de la page&quot; enregistre la durée passée par un visiteur sur la page. Elle utilise les étapes suivantes pour mesurer le calcul :

1. Pour un accès donné, observez l’horodatage.
2. Comparez cet accès à l’horodatage du prochain accès de la visite. La vue de page et le suivi des liens comptabilisent tous les accès.
3. La durée écoulée entre ces deux accès contribue au temps passé.

Cette dimension est utile pour comprendre la durée d’interaction des visiteurs avec une mesure donnée sur votre site.

>[!TIP]
>
>La durée de la visite n’est pas mesurée pour le dernier accès de la visite, car aucune demande d’image ultérieure ne permet de mesurer le temps écoulé. Ce concept s’applique également aux visites consistant en un seul accès (un rebond).

Cette dimension est basée sur les accès, ce qui signifie que la valeur est différente pour chaque accès. Comparez cette dimension à [Durée de la visite](time-spent-per-visit.md), qui est une dimension basée sur les visites. Plus le temps passé est long, plus le visiteur reste longtemps sur une page (accès).

![Durée de consultation de la page](../metrics/assets/time-spent2.png)

## Renseigner cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Si une suite de rapports contient des données, cette dimension fonctionne.

## Valeurs de dimension

Il existe plusieurs dimensions pour la durée de consultation de la page :

* **Durée de consultation de la page - cumulée**: La durée est cumulée. Les valeurs de dimension vont `"Less than 15 seconds"` de à `"More than 30 minutes"`. La durée entre les vues de page ne dure généralement pas plus de 30 minutes ; toutefois, le délai entre les vues de page peut dépasser 30 minutes si vous utilisez des accès horodatés ou des sources de données.
* **Durée de consultation de la page - granulaire**: Chaque nombre de secondes est une valeur de dimension unique.

Voir Présentation [de la](../metrics/time-spent.md) durée de la visite pour obtenir des informations plus générales sur la durée de la visite.
