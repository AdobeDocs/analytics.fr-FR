---
title: Minute
description: La minute à laquelle la mesure a été effectuée.
feature: Dimensions
exl-id: 63f13083-321f-4fd8-9352-e413e1ebf168
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 91%

---

# Minute

La &quot;minute&quot; [dimension](overview.md) rapporte la minute à laquelle une mesure donnée a été effectuée (arrondie à l’unité inférieure). Le premier élément de dimension correspond à la première minute de la période, et le dernier élément de dimension correspond à la dernière minute de la période. Cette dimension est importante pour les rapports de tendance, car elle vous permet d’afficher les mesures au fil du temps. Compte tenu de la granularité de cette dimension, Adobe recommande de limiter la période du rapport à un ou deux jours.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de dimension

Les éléments de dimension incluent une minute donnée dans la période d’un rapport, ainsi que la date correspondante. Celui-ci a la forme `HH:MM YYYY-MM-DD`. Les éléments de dimension commençant par `00:00` indiquent minuit ce jour-là, tandis que les valeurs commençant par `23:59` indiquent 23 h 59 ce jour-là.
