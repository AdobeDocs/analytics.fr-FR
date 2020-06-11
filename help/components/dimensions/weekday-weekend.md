---
title: Jour ouvrable/week-end
description: Détermine si l’accès s’est produit pendant une semaine ou un week-end.
translation-type: tm+mt
source-git-commit: 05ea2778cd5cd324c660fd0f1d2ac02373829f0f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 3%

---


# Jour ouvrable/week-end

La dimension &quot;Jour de la semaine/Fin de semaine&quot; permet de savoir si l’accès s’est produit au cours d’un jour de la semaine (du lundi au vendredi) ou d’un week-end (du samedi au dimanche). The time of the hit is based on the [report suite&#39;s time zone](/help/admin/admin/general-acct-settings-admin.md).

## Renseigner cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Si une suite de rapports contient des données, cette dimension fonctionne.

## Valeurs de dimension

Cette dimension contient toujours exactement deux valeurs de dimension : `"Weekday"` et `"Weekend"`. La valeur de dimension `"Weekday"` s’applique à tous les accès du lundi au vendredi, tandis que la valeur de dimension `"Weekend"` s’applique à tous les accès du samedi et du dimanche.
