---
title: Semaine
description: La semaine au cours de laquelle la mesure a été effectuée.
feature: Dimensions
exl-id: 944ec843-998c-473f-b8e6-16cf126745b4
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 92%

---

# Semaine

La &quot;Semaine&quot; [dimension](overview.md) indique la semaine au cours de laquelle une mesure donnée a été effectuée. Le premier élément de dimension correspond à la première semaine de la période et le dernier élément de dimension correspond à la dernière semaine de la période. Cette dimension est essentielle pour les rapports de tendance, car elle vous permet d’afficher les mesures au fil du temps.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de dimension

Dans Analysis Workspace, les éléments de dimension comprennent la date (mois, jour et année) du premier jour de la semaine.

Dans Data Warehouse, les éléments de dimension comprennent des semaines numérotées en fonction de la période de la requête. Par exemple, la première semaine complète est `"Week 1"`. Si une requête inclut une semaine partielle, les données sont regroupées dans l’élément de dimension `"Week 0"`.
