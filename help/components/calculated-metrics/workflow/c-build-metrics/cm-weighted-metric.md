---
description: Découvrez des exemples de mesures filtrées et pondérées.
title: Mesures Filtrées Et Pondérées
feature: Calculated Metrics
exl-id: bea46e03-7d05-44c8-b654-c61b1e32becc
TQID: https://experienceleague.adobe.com/Euk3sI0-AYtfmpEbL-8gfWU4HcFE6kGO6QGgctZbvig
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 158
ht-degree: 63%

---

# Mesures filtrées et pondérées

Cet article présente des exemples de mesures filtrées et pondérées.

## Taux de rebond filtré

Cette mesure filtrée simple affiche le taux de rebond, uniquement pour les pages comportant plus de 100 visites :

![&#x200B; Taux de rebond filtré &#x200B;](assets/filtered-bounce-rate.png){zoomable="yes"}

Gardez à l’esprit que cette formule dépend d’une période cohérente. Si vous exécutez un rapport pour un seul jour, toute page comportant plus de 20 visiteurs présente un vif intérêt. Si vous exécutez pour un mois, vous souhaitez sans doute que le filtre inclut plus de visites.

## Taux de rebond filtré avec percentile

Ce filtre affiche le taux de rebond des 30 % les plus consultés des pages, lorsqu’ils sont triés par visites.

![Taux de rebond filtré avec percentile](assets/filtered-bounce-rate-with-percentile.png){zoomable="yes"}

## Taux de rebond pondéré

Supposons que vous souhaitiez trier par taux de rebond en général mais que les pages avec des visites supérieures doivent être plus élevées sur la liste. Vous pouvez créer un taux de rebond pondéré qui ressemble à ceci :

![](assets/weighted-bounce-rate.png)
