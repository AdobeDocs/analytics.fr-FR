---
title: Minute
description: minute à laquelle la mesure s’est produite.
translation-type: tm+mt
source-git-commit: 2c262e5345c39a71a6a54062c607273528294b24
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 1%

---


# Minute

La dimension &quot;Minute&quot; rapporte la minute à laquelle une mesure donnée a eu lieu (arrondie à la fin). La première valeur de dimension correspond à la première minute de la période et la dernière à la dernière minute de la période. Cette dimension est utile pour les rapports de tendances, car elle vous permet d’afficher les mesures au fil du temps. Etant donné la granularité de cette dimension, Adobe recommande de limiter la plage de dates du rapports à un ou deux jours.

## Renseigner cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Si une suite de rapports contient des données, cette dimension fonctionne.

## Valeurs de dimension

Les valeurs de dimension incluent une minute donnée dans la plage de dates d’un rapport, ainsi que sa date. Il est mis en forme `HH:MM YYYY-MM-DD`. Les valeurs de dimension commençant par `00:00` équivalent à minuit ce jour-là, tandis que les valeurs commençant par `23:59` égale à 23h59 pour ce jour-là.
