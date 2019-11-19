---
description: Affiche le temps passé par les visiteurs sur la page.
solution: Analytics
title: Durée de consultation de la page
topic: Reports
translation-type: tm+mt
source-git-commit: df64b85f2567df68d2f710762596e4960214a4f6

---


# Time spent on page (Durée de consultation de la page)

Adobe Analytics propose plusieurs méthodes pour déterminer le temps passé dans les rapports Analytics. Dans la plupart des cas, la durée de la visite est calculée en procédant comme suit :

1. Pour un accès donné, observez l’horodatage et la valeur de dimension.
2. Comparez cet accès à l’horodatage du prochain accès de la visite.
3. Le temps passé entre ces deux accès contribue au temps passé pour cette page.

Lors de l’affichage des données de dimension Durée de consultation, gardez à l’esprit les points suivants :

* Le temps passé prend en compte l’attribution et l’expiration.
* Les types d’accès Pages vues et Suivi de liens sont pris en compte lors du calcul des données de durée de consultation.
* Le temps passé n’est pas mesuré lors du dernier accès de la visite, puisqu’il n’existe aucune demande d’image ultérieure pour mesurer le temps écoulé.
* Les rebonds ne peuvent pas mesurer le temps passé, car la visite consiste en un seul accès.

Le temps passé sur la page mesure le temps écoulé entre les accès d’une visite. Il existe des dimensions distinctes entre les dimensions **granulaire** et les dimensions **empilées**.

* **** Granulaire : Chaque valeur de dimension est un nombre de secondes différent passé entre deux accès.
* **** Regroupement : Chaque valeur de dimension est un compartiment prédéfini :
   * Moins de 15 secondes
   * 15 à 29 secondes
   * 1 à 3 minutes
   * 3 à 5 minutes
   * 5 à 10 minutes
   * 10 à 15 minutes
   * 15 à 20 minutes
   * 20 à 30 minutes
   * Plus de 30 minutes

Cette dimension est basée sur les accès, qui, si elle est utilisée comme ventilation, peuvent fournir des données plus significatives. Comparez cette dimension au [temps passé par visite](reports-time-spent-per-visit.md), qui est une dimension basée sur les visites.

![Temps passé](/help/components/c-variables/c-metrics/assets/time-spent1.png)
