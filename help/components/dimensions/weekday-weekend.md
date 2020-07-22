---
title: Jour ouvrable/week-end
description: Détermine si l’accès s’est produit pendant une semaine ou un week-end.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 3%

---


# Jour ouvrable/week-end

La dimension &quot;Jour de la semaine/Fin de semaine&quot; permet de savoir si l’accès s’est produit au cours d’un jour de la semaine (du lundi au vendredi) ou d’un week-end (du samedi au dimanche). The time of the hit is based on the [report suite&#39;s time zone](/help/admin/admin/general-acct-settings-admin.md).

## Renseigner cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Si une suite de rapports contient des données, cette dimension fonctionne.

## Éléments de dimension

Cette dimension contient toujours exactement deux éléments de dimension : `"Weekday"` et `"Weekend"`. L’élément de dimension `"Weekday"` s’applique à tous les accès du lundi au vendredi, tandis que l’élément de dimension `"Weekend"` s’applique à tous les accès les samedis et dimanches.
