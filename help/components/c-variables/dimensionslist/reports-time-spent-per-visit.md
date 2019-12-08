---
description: valeur nulle
title: Durée de la visite
topic: Reports
uuid: 76441e36-b7fe-4cf3-8d72-c51d558afa13
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Durée de la visite

Adobe Analytics propose plusieurs méthodes pour déterminer le temps passé dans les rapports Analytics. Dans la plupart des cas, la durée de la visite est calculée en procédant comme suit :

1. Pour une visite donnée, observez l’horodatage du premier accès.
2. Comparez cet accès à l’horodatage du dernier accès de la visite.
3. La durée écoulée entre ces deux accès détermine le temps passé lors de cette visite.

Lors de l’affichage des données de dimension sur la durée de la visite, tenez compte des points suivants :

* Les types d’accès Pages vues et Suivi de liens sont pris en compte lors du calcul des données de durée de la visite.
* Le temps passé n’est pas mesuré lors du dernier accès de la visite, puisqu’il n’existe aucune demande d’image ultérieure pour mesurer le temps écoulé.
* Les rebonds ne peuvent pas mesurer le temps passé, car la visite consiste en un seul accès.

La durée de la visite mesure le temps total passé lors d’une visite. Il existe des dimensions distinctes entre **Granulaire** et **Regroupement**.

* **Granulaire** : chaque valeur de dimension correspond à un nombre de secondes différent qui composent une visite.
* **Regroupement** : chaque valeur de dimension est un groupe prédéfini :
   * Moins de 1 minute
   * 1-5 minutes
   * 5-10 minutes
   * 30-60 minutes
   * 1-2 heures
   * 2-5 heures
   * 5-10 heures
   * 10-15 heures
   * Plus de 15 heures

> [!NOTE] Les [visites](../c-metrics/metrics-visit.md) se terminent généralement après 12 heures d’activité. Toutefois, les visites peuvent dépasser 12 heures si vous utilisez des sources de données ou des accès horodatés.

Cette dimension est basée sur les visites. Comparez cette dimension à la [durée de consultation de la page](reports-time-spent-on-page.md), qui est une dimension basée sur les accès.
