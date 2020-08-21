---
title: Mot-clé de recherche
description: Le mot-clé de recherche utilisé par le visiteur pour accéder à votre site.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 78%

---


# Mot-clé de recherche

La dimension « Mot-clé de recherche » indique les mots-clés de recherche que les visiteurs utilisent pour accéder à votre site.

>[!IMPORTANT]
>
>La plupart des moteurs de recherche ne transmettent plus le mot-clé de recherche en raison de l’augmentation des pratiques de confidentialité. Hits where Adobe recognizes a search engine but is missing a keyword groups under the dimension item `"Keyword unavailable"`.

Un référent doit répondre aux deux critères suivants pour être qualifié de mot-clé de recherche :

* Le domaine référent est reconnu par Adobe comme un [moteur de recherche](search-engine.md) valide.
* Il existe un paramètre de chaîne de requête de mot-clé dans l’URL de référence. If the keyword query string exists but does not contain a value, it groups under the dimension item `"Keyword unavailable"`.

Si vous souhaitez distinguer le référencement payant du référencement naturel, la [détection de référencement payant](/help/admin/admin/paid-search-detection/paid-search-detection.md) est requise. Plusieurs dimensions sont disponibles pour les mots-clés de recherche :

* **Mot-clé de recherche** : le mot-clé de recherche utilisé pour accéder à votre site, qu’il soit payant ou naturel.
* **Mot-clé de recherche - payant** : le mot-clé de recherche utilisé pour accéder à votre site, qui correspond à la détection de référencement payant.
* **Mot-clé de recherche - naturel** : le mot-clé de recherche utilisé pour accéder à votre site, qui ne correspond pas à la détection de référencement payant.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à plusieurs tables de recherche internes à Adobe. Chaque valeur est basée sur le [référent](referrer.md) de l’accès, qui dépend des [filtres d’URL internes](/help/admin/admin/internal-url-filter-admin.md). Veillez à configurer correctement la dimension Référent et les filtres d’URL internes.

## Éléments de Dimension

Les éléments de Dimension incluent les mots-clés de recherche utilisés pour atteindre votre site. The `"Unspecified"` dimension item is all non-search traffic.
