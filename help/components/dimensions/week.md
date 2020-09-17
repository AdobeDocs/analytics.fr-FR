---
title: Semaine
description: La semaine au cours de laquelle la mesure a été effectuée.
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 42%

---


# Semaine

La dimension « Semaine » indique la semaine au cours de laquelle une mesure donnée a été effectuée. Le premier élément de dimension est la première semaine de la période et le dernier élément de dimension est la dernière semaine de la période. Cette dimension est essentielle pour les rapports de tendance, car elle vous permet d’afficher les mesures au fil du temps.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de Dimension

En Analysis Workspace, les éléments de dimension incluent la date (mois, jour et année) du premier jour de la semaine.

En Data Warehouse, les éléments de dimension incluent des semaines numérotées en fonction de la plage de dates de la requête. Par exemple, la première semaine complète est `"Week 1"`. Si une requête inclut une semaine partielle, les données sont regroupées dans l’élément de dimension `"Week 0"`.
