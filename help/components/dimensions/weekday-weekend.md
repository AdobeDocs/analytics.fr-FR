---
title: Jour ouvrable/week-end
description: Détermine si l’accès s’est produit pendant un jour ouvrable ou le week-end.
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 80%

---

# Jour ouvrable/week-end

La [dimension](overview.md) Jour de la semaine/week-end indique si l’accès a eu lieu un jour de la semaine (lundi à vendredi) ou un week-end (samedi à dimanche) dans insight. L’heure de l’accès est basée sur le [fuseau horaire de la suite de rapports](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de dimension

Cette dimension contient toujours exactement deux éléments de dimension : `"Weekday"` et `"Weekend"`. L’élément de dimension `"Weekday"` s’applique à tous les accès du lundi au vendredi, tandis que l’élément de dimension `"Weekend"` s’applique à tous les accès du samedi au dimanche.
