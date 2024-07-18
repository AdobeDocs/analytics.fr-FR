---
title: Heure
description: L’heure au cours de laquelle la mesure a été effectuée.
feature: Dimensions
exl-id: 323c46dd-87d0-487a-b954-e5ccbc1b919d
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 94%

---

# Heure

L’ [dimension](overview.md) &quot;Heure&quot; indique l’heure à laquelle une mesure donnée a été effectuée (arrondie). Le premier élément de dimension correspond à la première heure de la période et le dernier élément de dimension correspond à la dernière heure de la période. Cette dimension est importante pour les rapports de tendance, car elle vous permet d’afficher les mesures au fil du temps.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de dimension

Les éléments de dimension comprennent une heure donnée se trouvant dans la période d’un rapport, à côté de sa date. Celui-ci a la forme `HH:HH YYYY-MM-DD`.

## Heure d’été

L’heure d’été est une pratique qui consiste à avancer les horloges d’une heure au printemps et à les reculer d’une heure à l’automne. Si le fuseau horaire d’une suite de rapports utilise l’heure d’été, Adobe adapte les données en fonction de cette heure.

* **Début de l’heure d’été** : en mars, les rapports indiquent généralement un décalage d’une heure dans les données au début de l’heure d’été. L’heure n’existe pas, elle ne fait donc pas partie de la collecte de données. Notez qu’une petite quantité de données peut encore se trouver dans cette heure. Les serveurs de collecte de données d’Adobe prennent plusieurs secondes (jusqu’à une minute) pour tenir compte des ajustements à l’heure d’été.
* **Fin de l’heure d’été** : en novembre, les rapports indiquent généralement une heure doublée à la fin de l’heure d’été. L’heure apparaissant deux fois, les deux heures sont agrégées dans les rapports.
