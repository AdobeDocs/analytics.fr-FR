---
title: Minute
description: La minute à laquelle la mesure a été effectuée.
feature: Dimensions
exl-id: 63f13083-321f-4fd8-9352-e413e1ebf168
TQID: https://experienceleague.adobe.com/GRivRprXBteGxRZieSI3uyjHALDJ-0hHbZx3S9ldJW0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 146
ht-degree: 76%

---

# Minute

La [dimension](overview.md) Minute indique la minute à laquelle une mesure donnée a été effectuée (arrondie à l’unité inférieure). Le premier élément de dimension correspond à la première minute de la période, et le dernier élément de dimension correspond à la dernière minute de la période. Cette dimension est importante pour les rapports de tendance, car elle vous permet d’afficher les mesures au fil du temps. Compte tenu de la granularité de cette dimension, Adobe recommande de limiter la période du rapport à un ou deux jours.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de dimension

Les éléments de dimension incluent une minute donnée dans la période d’un rapport, ainsi que la date correspondante. Celui-ci a la forme `HH:MM YYYY-MM-DD`. Les éléments Dimension commençant par `00:00` correspondent à minuit ce jour-là, tandis que les valeurs commençant par `23:59` correspondent à 23 :59 pour ce jour-là.
