---
title: Jour ouvrable/week-end
description: Détermine si l’accès s’est produit pendant un jour ouvrable ou le week-end.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 68%

---


# Jour ouvrable/week-end

La dimension « Jour ouvrable/week-end » permet de savoir si l’accès s’est produit un jour ouvrable (du lundi au vendredi) ou le week-end (du samedi au dimanche). L’heure de l’accès est basée sur le [fuseau horaire de la suite de rapports](/help/admin/admin/general-acct-settings-admin.md).

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de Dimension

This dimension always contains exactly two dimension items: `"Weekday"` and `"Weekend"`. The dimension item `"Weekday"` applies to all hits Monday through Friday, while the dimension item `"Weekend"` applies to all hits on Saturday and Sunday.
