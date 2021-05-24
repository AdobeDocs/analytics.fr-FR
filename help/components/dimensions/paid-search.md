---
title: Référencement payant
description: Permet de distinguer les mesures de référencement payant des mesures de référencement naturel.
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '148'
ht-degree: 100%

---

# Référencement payant

La dimension « Référencement payant » vous permet d’examiner n’importe quelle mesure et de la comparer avec le référencement payant et le référencement naturel. Tous les autres accès en dehors des moteurs de recherche sont omis. Cette dimension permet de comparer les tâches de référencement payant à celles du référencement organique.

## Renseignement de cette dimension avec des données

Pour que cette dimension fonctionne correctement, il suffit de configurer correctement la [Détection de référencement payant](/help/admin/admin/paid-search-detection/paid-search-detection.md) dans les paramètres de la suite de rapports. Si la détection de référencement payant est correctement configurée et qu’une suite de rapports comporte des données, cette dimension fonctionne toujours.

## Éléments de dimension

Les éléments de dimension comprennent deux valeurs statiques : `"Natural"` et `"Paid"`. Si une visite correspond à la fois aux critères d’un moteur de recherche et à la détection de référencement payant, elle appartient à l’élément de dimension `"Paid"`. Si une visite correspond aux critères d’un moteur de recherche et ne correspond *pas* à la détection de référencement payant, elle appartient à l’élément de dimension `"Natural"`.
