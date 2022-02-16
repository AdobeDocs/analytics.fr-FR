---
title: FAQ sur Data Warehouse
description: Questions fréquentes sur Data Warehouse
feature: Data Warehouse
exl-id: 51c3ba17-a8b2-4030-9521-355ebbbfcd0d
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 100%

---

# FAQ sur Data Warehouse

Questions fréquentes sur Data Warehouse

## Lorsque j’utilise le menu déroulant de granularité lors de la création d’une requête, à quel format de dates doit-on s’attendre ?

Lors de l’application de la granularité dans une requête Data Warehouse, la colonne « Date » est ajoutée au rapport. En fonction de la granularité sélectionnée, le format de date change.

| Granularité | Format | Exemple |
| --- | --- | --- |
| Toutes les heures | `mmmm d, yyyy` Heure `H` | 1er janvier 20XX, heure 0 |
| Quotidien | `mmmm d, yyyy` | 1er janvier 20XX |
| Hebdomadaire | Semaine `w, yyyy` | Semaine 1, 20XX |
| Mensuel | `mmmm yyyy` | Janvier 20XX |
| Trimestriel | `q` Trimestre `yyyy` | 1er trimestre 20XX |
| Annuel | `yyyy` | 20XX |

## Comment fonctionnent les segments comme dimensions dans Data Warehouse ?

Lorsque vous utilisez un segment comme une dimension dans Data Warehouse, le rapport renvoie une colonne contenant `"0"` ou `"1"` :

* **`"0"`** : l’élément de dimension ne répondait pas aux critères du segment.
* **`"1"`** : l’élément de dimension répondait aux critères du segment.
