---
title: Minute
description: La minute à laquelle la mesure a été effectuée.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '145'
ht-degree: 100%

---


# Minute

La dimension « Minute » indique la minute à laquelle une mesure donnée a été effectuée (arrondie à l’unité inférieure). Le premier élément de dimension correspond à la première minute de la période, et le dernier élément de dimension correspond à la dernière minute de la période. Cette dimension est importante pour les rapports de tendance, car elle vous permet d’afficher les mesures au fil du temps. Compte tenu de la granularité de cette dimension, Adobe recommande de limiter la période du rapport à un ou deux jours.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de dimension

Les éléments de dimension incluent une minute donnée dans la période d’un rapport, ainsi que la date correspondante. Celui-ci a la forme `HH:MM YYYY-MM-DD`. Les éléments de dimension commençant par `00:00` indiquent minuit ce jour-là, tandis que les valeurs commençant par `23:59` indiquent 23 h 59 ce jour-là.
