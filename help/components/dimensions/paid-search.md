---
title: Recherche payante
description: Distingue les mesures des recherches payantes et naturelles.
translation-type: tm+mt
source-git-commit: d71edc74644907b47bfb6492e7a6c47c06d5984f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---


# Recherche payante

La dimension &quot;Recherche payante&quot; vous permet d’examiner n’importe quelle mesure et de la comparer entre la recherche payante et la recherche naturelle. Tous les autres accès en dehors des moteurs de recherche sont omis. Cette dimension permet de comparer vos efforts de recherche payante à ceux de la recherche organique.

## Renseigner cette dimension avec des données

Pour que cette dimension fonctionne correctement, il suffit de configurer correctement la détection [de recherche](/help/admin/admin/paid-search-detection/paid-search-detection.md) payante dans les paramètres de la suite de rapports. Si la détection des recherches payantes est correctement configurée et qu’une suite de rapports comporte des données, cette dimension fonctionne toujours.

## Valeurs de dimension

Les valeurs de dimension comprennent deux valeurs statiques : `"Natural"` et `"Paid"`. Si une visite correspond aux critères d&#39;un moteur de recherche et correspond également à la détection des recherches payantes, elle appartient à la valeur de la `"Paid"` dimension. Si une visite correspond à des critères pour un moteur de recherche et ne correspond *pas* à la détection de recherche payante, elle appartient à la valeur de `"Natural"` dimension.
