---
title: Moteur de recherche
description: Moteur de recherche utilisé par le visiteur pour accéder à votre site.
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 93%

---

# Moteur de recherche

La [dimension](overview.md) « Moteur de recherche » indique les moteurs de recherche que les visiteurs et visiteuses utilisent pour accéder à votre site. Un référent doit répondre aux deux critères suivants pour être classé comme moteur de recherche :

* Le domaine référent est reconnu par Adobe comme un moteur de recherche valide ;
* Il existe un paramètre de chaîne de requête de mot-clé dans l’URL de référence. Le paramètre de chaîne de requête peut être vide (c’est le cas de plusieurs moteurs de recherche en raison de leurs pratiques de confidentialité).

Si vous souhaitez distinguer le référencement payant du référencement naturel, la [détection de référencement payant](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md) est requise. Plusieurs dimensions sont disponibles pour les moteurs de recherche :

* **Moteur de recherche** : moteur de recherche utilisé pour atteindre votre site, qu’il s’agisse d’une recherche payante ou naturelle.
* **Moteur de recherche - Payant** : moteur de recherche utilisé pour atteindre votre site et ayant déclenché une détection de référencement payant.
* **Moteur de recherche - Naturel** : moteur de recherche utilisé pour atteindre votre site et n’ayant pas déclenché de détection de référencement payant.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à plusieurs tables de recherche internes à Adobe. Chaque valeur est basée sur le [référent](referrer.md) de l’accès, qui dépend des [filtres d’URL internes](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md). Veillez à configurer correctement la dimension Référent et les filtres d’URL internes.

## Éléments de dimension

Les éléments de dimension comprennent les moteurs de recherche utilisés pour accéder à votre site. Les exemples de valeurs comprennent `"Google"`, `"Microsoft Bing"` et `"DuckDuckGo"`. L’élément de dimension `"Unspecified"` correspond à l’ensemble du trafic hors recherche.
