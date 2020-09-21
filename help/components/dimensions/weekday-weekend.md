---
title: Jour ouvrable/week-end
description: Détermine si l’accès s’est produit pendant un jour ouvrable ou le week-end.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '105'
ht-degree: 100%

---


# Jour ouvrable/week-end

La dimension « Jour ouvrable/week-end » permet de savoir si l’accès s’est produit un jour ouvrable (du lundi au vendredi) ou le week-end (du samedi au dimanche). L’heure de l’accès est basée sur le [fuseau horaire de la suite de rapports](/help/admin/admin/general-acct-settings-admin.md).

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de dimension

Cette dimension contient toujours exactement deux éléments de dimension : `"Weekday"` et `"Weekend"`. L’élément de dimension `"Weekday"` s’applique à tous les accès du lundi au vendredi, tandis que l’élément de dimension `"Weekend"` s’applique à tous les accès du samedi au dimanche.
