---
title: Moteur de recherche
description: Moteur de recherche utilisé par le visiteur pour accéder à votre site.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 1%

---


# Moteur de recherche

La dimension &quot;Moteur de recherche&quot; rapporte les moteurs de recherche que les visiteurs utilisent pour accéder à votre site. Un parrain doit répondre aux deux critères suivants pour être classé comme moteur de recherche :

* Le domaine référent est reconnu par Adobe comme un moteur de recherche valide ;
* Il existe un paramètre de chaîne de requête de mot-clé dans l’URL de référence. Le paramètre de chaîne de requête peut être vide (comme c&#39;est le cas pour plusieurs moteurs de recherche en raison de pratiques de confidentialité).

Si vous souhaitez distinguer la recherche payée de la recherche naturelle, la détection [de la recherche](/help/admin/admin/paid-search-detection/paid-search-detection.md) payée est requise. Plusieurs dimensions sont disponibles pour les moteurs de recherche :

* **Moteur** de recherche : Moteur de recherche utilisé pour atteindre votre site, qu&#39;il soit payant ou naturel.
* **Moteur de recherche - payé**: Moteur de recherche utilisé pour atteindre votre site, qui correspondait à la détection des recherches payantes.
* **Moteur de recherche - naturel**: Moteur de recherche utilisé pour atteindre votre site, qui ne correspondait pas à la détection des recherches payantes.

## Renseigner cette dimension avec des données

Cette dimension fait référence à plusieurs tables de recherche internes à Adobe. Chaque valeur est basée sur le [parrain](referrer.md) de l’accès, qui dépend des filtres [d’URL](/help/admin/admin/internal-url-filter-admin.md)internes. Assurez-vous que la dimension de parrain et les filtres d’URL internes sont correctement configurés.

## Éléments de dimension

Les éléments de dimension incluent les moteurs de recherche utilisés pour atteindre votre site. Example values include `"Google"`, `"Microsoft Bing"`, and `"DuckDuckGo"`. L’élément `"Unspecified"` de dimension est tout le trafic non lié à la recherche.
