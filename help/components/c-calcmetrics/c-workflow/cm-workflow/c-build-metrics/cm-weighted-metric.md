---
description: Affiche des exemples de mesures filtrées et pondérées.
title: Mesures filtrées et pondérées
feature: Calculated Metrics
exl-id: bea46e03-7d05-44c8-b654-c61b1e32becc
source-git-commit: bf58da2a39e8b9fd298356f23a9bf8f6c394d3de
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 89%

---

# Mesures filtrées et pondérées

Cet article présente des exemples de mesures filtrées et pondérées.

## Taux de rebond filtré 

Cette mesure filtrée simple affiche le taux de rebond, uniquement pour les pages comportant plus de 100 visites :

![ Taux de rebond filtré ](assets/filtered-bounce-rate.png){zoomable="yes"}

Gardez à l’esprit que cette formule dépend d’une période cohérente. Si vous exécutez un rapport pour un seul jour, toute page comportant plus de 20 visiteurs présente un vif intérêt. Si vous exécutez pour un mois, vous souhaitez sans doute que le filtre inclut plus de visites.

## Taux de rebond filtré avec percentile 

Ce filtre affiche le taux de rebond pour les 30 % supérieurs des pages, lors du tri par visite.

![Taux de rebond filtré avec percentile](assets/filtered-bounce-rate-with-percentile.png){zoomable="yes"}

## Mesure pondérée 

Supposons que vous souhaitiez trier par taux de rebond en général mais que les pages avec des visites supérieures doivent être plus élevées sur la liste. Vous pouvez créer un taux de rebond pondéré qui ressemble à ceci :

![](assets/weighted-bounce-rate.png)
