---
title: Mot-clé de recherche
description: Mot-clé de recherche utilisé par le visiteur pour accéder à votre site.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---


# Mot-clé de recherche

La dimension Mot-clé de recherche rapporte les mots-clés de recherche que les visiteurs utilisent pour accéder à votre site.

>[!IMPORTANT] La plupart des moteurs de recherche ne transmettent plus le mot-clé de recherche en raison des pratiques de confidentialité croissantes. Accès où Adobe reconnaît un moteur de recherche mais manque un groupe de mots-clés sous la valeur de dimension `"Keyword unavailable"`.

Un parrain doit répondre aux deux critères suivants pour être classé comme mot-clé de recherche :

* Le domaine référent est reconnu par Adobe comme un moteur [de](search-engine.md)recherche valide ;
* Il existe un paramètre de chaîne de requête de mot-clé dans l’URL de référence. Si la chaîne de requête de mot-clé existe mais ne contient pas de valeur, elle est regroupée sous la valeur de dimension `"Keyword unavailable"`.

Si vous souhaitez distinguer la recherche payée de la recherche naturelle, la détection [de la recherche](/help/admin/admin/paid-search-detection/paid-search-detection.md) payée est requise. Plusieurs dimensions sont disponibles pour les mots-clés de recherche :

* **Mot-clé** de recherche : Mot-clé de recherche utilisé pour atteindre votre site, qu&#39;il soit payant ou naturel.
* **Mot-clé de recherche - payé**: Mot-clé de recherche utilisé pour atteindre votre site, qui correspondait à la détection des recherches payantes.
* **Mot-clé de recherche - naturel**: Mot-clé de recherche utilisé pour atteindre votre site, qui ne correspondait pas à la détection des recherches payantes.

## Renseigner cette dimension avec des données

Cette dimension fait référence à plusieurs tables de recherche internes à Adobe. Chaque valeur est basée sur le [parrain](referrer.md) de l’accès, qui dépend des filtres [d’URL](/help/admin/admin/internal-url-filter-admin.md)internes. Assurez-vous que la dimension de parrain et les filtres d’URL internes sont correctement configurés.

## Valeurs de dimension

Les valeurs de dimension incluent les mots-clés de recherche utilisés pour atteindre votre site. La valeur `"Unspecified"` de dimension correspond à tout le trafic hors recherche.
