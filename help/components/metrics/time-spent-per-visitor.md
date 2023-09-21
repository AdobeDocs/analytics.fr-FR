---
title: Durée par visiteur (secondes)
description: La mesure « Durée par visiteur (secondes) » indique la durée moyenne d’interaction des visiteurs avec un élément de dimension donné au cours de l’ensemble de la durée de vie d’un visiteur.
feature: Metrics
exl-id: 80f38bab-2ee1-4d0d-ba53-9b2c7c85e481
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 100%

---

# Durée par visiteur (secondes)

La mesure [!UICONTROL Durée par visiteur (secondes)] indique la durée moyenne d’interaction des visiteurs avec un élément de dimension donné au cours de l’ensemble de la durée de vie d’un visiteur.[](overview.md)

Cette mesure n’est pas disponible dans Data Warehouse en raison de sa différence d’architecture de traitement.

## Méthode de calcul de cette mesure

Cette mesure utilise la formule [`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md).

## Pourcentages supérieurs à 100 %

Cette mesure contient souvent des pourcentages supérieurs à 100 %. Le dénominateur correspond à la durée par visiteur pour la dimension entière, tandis que le numérateur correspond à la durée par visiteur de l’élément de dimension. Si la durée par visiteur de la dimension entière est inférieure à la durée par visiteur d’un élément de dimension donné, les pourcentages sont supérieurs à 100 %. Le tri des rapports de classement selon cette mesure affiche une durée par visiteur anormale, ce qui n’a généralement pas de valeur. Adobe recommande de trier selon une autre mesure, telle que [Visites](visits.md), dans les rapports de classement.

Consultez [Présentation de la durée de consultation](time-spent.md) pour obtenir des informations plus générales sur la durée de consultation.
