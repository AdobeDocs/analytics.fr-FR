---
title: Jour ouvrable/week-end
description: Détermine si l’accès s’est produit pendant un jour ouvrable ou le week-end.
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 80%

---

# Jour ouvrable/week-end

&#39;Jour ouvrable/week-end&#39; [dimension](overview.md) fournit des informations sur les occurrences de l’accès pendant un jour de semaine (du lundi au vendredi) ou le week-end (du samedi au dimanche). L’heure de l’accès est basée sur le [fuseau horaire de la suite de rapports](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md).

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de dimension

Cette dimension contient toujours exactement deux éléments de dimension : `"Weekday"` et `"Weekend"`. L’élément de dimension `"Weekday"` s’applique à tous les accès du lundi au vendredi, tandis que l’élément de dimension `"Weekend"` s’applique à tous les accès du samedi au dimanche.
