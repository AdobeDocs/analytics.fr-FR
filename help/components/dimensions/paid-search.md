---
title: Référencement payant
description: Permet de distinguer les mesures de référencement payant des mesures de référencement naturel.
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 100%

---

# Référencement payant

La dimension « Référencement payant » vous permet d’examiner n’importe quelle mesure et de la comparer avec le référencement payant et le référencement naturel. Tous les autres accès en dehors des moteurs de recherche sont omis. Cette dimension permet de comparer les tâches de référencement payant à celles du référencement organique.

## Renseignement de cette dimension avec des données

Pour que cette dimension fonctionne correctement, il suffit de configurer correctement la [Détection de référencement payant](/help/admin/admin/paid-search-detection/paid-search-detection.md) dans les paramètres de la suite de rapports. Si la détection de référencement payant est correctement configurée et qu’une suite de rapports comporte des données, cette dimension fonctionne toujours.

## Éléments de dimension

Les éléments de dimension comprennent deux valeurs statiques : `"Natural"` et `"Paid"`. Si une visite correspond à la fois aux critères d’un moteur de recherche et à la détection de référencement payant, elle appartient à l’élément de dimension `"Paid"`. Si une visite correspond aux critères d’un moteur de recherche et ne correspond *pas* à la détection de référencement payant, elle appartient à l’élément de dimension `"Natural"`.
