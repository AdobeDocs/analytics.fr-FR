---
title: Heure
description: L’heure au cours de laquelle la mesure a été effectuée.
feature: Dimensions
exl-id: 323c46dd-87d0-487a-b954-e5ccbc1b919d
TQID: https://experienceleague.adobe.com/Gkigdxnrted-gkPoGCQMx229EvCmVvSt9Rr5QP-IfGU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 243
ht-degree: 94%

---

# Heure

La [dimension](overview.md) « Heure » indique l’heure à laquelle une mesure donnée a été effectuée (arrondie à l’unité inférieure). Le premier élément de dimension correspond à la première heure de la période et le dernier élément de dimension correspond à la dernière heure de la période. Cette dimension est importante pour les rapports de tendance, car elle vous permet d’afficher les mesures au fil du temps.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de dimension

Les éléments de dimension comprennent une heure donnée se trouvant dans la période d’un rapport, à côté de sa date. Celui-ci a la forme `HH:HH YYYY-MM-DD`.

## Heure d’été

L’heure d’été est une pratique qui consiste à avancer les horloges d’une heure au printemps et à les reculer d’une heure à l’automne. Si le fuseau horaire d’une suite de rapports utilise l’heure d’été, Adobe adapte les données en fonction de cette heure.

* **Début de l’heure d’été** : en mars, les rapports indiquent généralement un décalage d’une heure dans les données au début de l’heure d’été. L’heure n’existe pas, elle ne fait donc pas partie de la collecte de données. Notez qu’une petite quantité de données peut encore se trouver dans cette heure. Les serveurs de collecte de données d’Adobe prennent plusieurs secondes (jusqu’à une minute) pour tenir compte des ajustements à l’heure d’été.
* **Fin de l’heure d’été** : en novembre, les rapports indiquent généralement une heure doublée à la fin de l’heure d’été. L’heure apparaissant deux fois, les deux heures sont agrégées dans les rapports.
