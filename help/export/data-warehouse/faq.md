---
title: FAQ Data Warehouse
description: Questions fréquentes pour le Data Warehouse.
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 9%

---


# FAQ Data Warehouse

Questions fréquentes pour le Data Warehouse.

## Lorsque j’utilise la liste déroulante de granularité lors de la création d’une requête, quel format puis-je attendre pour les dates ?

Lors de l’application de la granularité dans une requête de Data Warehouse, la colonne Date est ajoutée au rapport. En fonction de la granularité sélectionnée, le format de date change.

| Granularité | Format | Exemple |
| --- | --- | --- |
| Toutes les heures | `mmmm d, yyyy` Heure `H` | 1er janvier, 20XX, heure 0 |
| Quotidien | `mmmm d, yyyy` | 1er janvier 20XX |
| Hebdomadaire | Semaine `w, yyyy` | Semaine 1, 20XX |
| Mensuel | `mmmm yyyy` | 20XX janvier |
| Trimestriel | `q` Trimestre `yyyy` | 1er trimestre 20XX |
| Annuel | `yyyy` | 20XX |

## Comment les segments en tant que dimensions fonctionnent-ils en Data Warehouse ?

Lorsque vous utilisez un segment en tant que dimension dans le Data Warehouse, le rapport renvoie une colonne contenant `"0"` ou `"1"` :

* **`"0"`**: L’élément de dimension ne répondait pas aux critères du segment.
* **`"1"`**: L’élément de dimension répondait aux critères du segment.
