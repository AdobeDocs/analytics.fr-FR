---
title: Moteur de recherche
description: Moteur de recherche utilisé par le visiteur pour accéder à votre site.
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
TQID: https://experienceleague.adobe.com/fOk6ypu24XzT6aypOHUAE-RYSW39wyrzkyt-lvOKy7Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 225
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
