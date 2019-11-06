---
description: Adobe Analytics propose différentes mesures et dimensions de durée de la visite. Découvrez-les ainsi que leur mode de calcul.
solution: Analytics
title: Durée de la visite
topic: Mesures
translation-type: tm+mt
source-git-commit: ee9a6462138fe3483ca8a4ba042cb4eb39536031

---


# Mesures Durée de consultation

Adobe Analytics propose plusieurs méthodes pour déterminer le temps passé dans les rapports Analytics. Dans la plupart des cas, la durée de la visite est calculée en procédant comme suit :

1. Pour un accès donné, observez l’horodatage et la valeur de dimension.
1. Comparez cet accès à l’horodatage du prochain accès de la visite.
1. La durée écoulée entre ces deux accès contribue au temps passé pour cette valeur de dimension.

Lors de l’affichage des mesures de durée de consultation, gardez à l’esprit les points suivants :

* Le temps passé prend en compte l’attribution et l’expiration.
* Les types d’accès Pages vues et Suivi de liens sont pris en compte lors du calcul des données de durée de consultation.
* Le temps passé n’est pas mesuré lors du dernier accès de la visite, puisqu’il n’existe aucune demande d’image ultérieure pour mesurer le temps écoulé.
* Les rebonds ne peuvent pas mesurer le temps passé, car la visite consiste en un seul accès.

## Durée totale (secondes)

Durée totale pendant laquelle tous les visiteurs ont interagi avec une valeur de dimension, mesurée en secondes.

## Temps passé par visite (secondes)

Durée moyenne pendant laquelle les visiteurs interagissent avec une valeur de dimension au cours d’une visite. Son calcul approximatif est `Total seconds spent / (Visits - Bounces)`.

## Durée par visiteur (secondes)

Durée moyenne pendant laquelle les visiteurs interagissent avec une valeur de dimension pendant toute la durée de vie du visiteur. Son calcul approximatif est `Total seconds spent / (Unique Visitors - Bounces)`.

## Durée moyenne de consultation du site (secondes)

Durée moyenne passée sur votre site avec la valeur de dimension donnée. Cette mesure est généralement associée à une dimension de date afin d’afficher la durée de consultation. Son calcul approximatif est `Total seconds spent / (Sequences - Bounces)`. Les séquences sont une série d’accès pour laquelle la valeur de dimension n’a pas changé. Dans la plupart des cas, utilisez la mesure Durée de la visite.

## Durée de consultation moyenne de la page

Disponible uniquement dans le créateur de rapports. Dans la plupart des cas, utilisez la mesure Durée de la visite.
