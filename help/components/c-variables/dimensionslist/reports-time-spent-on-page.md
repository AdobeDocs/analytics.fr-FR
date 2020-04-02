---
description: Affiche le temps passé par les visiteurs sur la page.
title: Durée de consultation de la page
topic: Reports
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Durée de consultation de la page

Adobe Analytics propose plusieurs méthodes pour déterminer le temps passé dans les rapports Analytics. Dans la plupart des cas, la durée de la visite est calculée en procédant comme suit :

1. Pour un accès donné, observez l’horodatage et la valeur de dimension.
2. Comparez cet accès à l’horodatage du prochain accès de la visite.
3. La durée écoulée entre ces deux accès contribue au temps passé pour cette page.

Lors de l’affichage des données de dimension sur la durée de la visite, tenez compte des points suivants :

* Le temps passé prend en compte l’attribution et l’expiration.
* Les types d’accès Pages vues et Suivi de liens sont pris en compte lors du calcul des données de durée de la visite.
* Le temps passé n’est pas mesuré lors du dernier accès de la visite, puisqu’il n’existe aucune demande d’image ultérieure pour mesurer le temps écoulé.
* Les rebonds ne peuvent pas mesurer le temps passé, car la visite consiste en un seul accès.

La durée de consultation de la page mesure le temps écoulé entre les accès d’une visite. Il existe des dimensions distinctes entre **Granulaire** et **Regroupement**.

* **Granulaire** : chaque valeur de dimension est un nombre de secondes différent passé entre deux accès.
* **Regroupement** : chaque valeur de dimension est un groupe prédéfini :
   * Moins de 15 secondes
   * 15 à 29 secondes
   * 1 à 3 minutes
   * 3 à 5 minutes
   * 5 à 10 minutes
   * 10 à 15 minutes
   * 15 à 20 minutes
   * 20 à 30 minutes
   * Plus de 30 minutes

Cette dimension est basée sur les accès, qui, si elle est utilisée comme ventilation, peut fournir des données plus significatives. Comparez cette dimension à [Durée de la visite](reports-time-spent-per-visit.md), qui est une dimension basée sur les visites.

![Durée](/help/components/c-variables/c-metrics/assets/time-spent1.png)
