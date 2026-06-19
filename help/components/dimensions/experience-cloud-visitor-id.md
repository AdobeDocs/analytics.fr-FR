---
title: Identifiant visiteur Experience Cloud
description: Experience Cloud ID (ECID) du visiteur, disponible dans Data Warehouse.
feature: Dimensions
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 105
ht-degree: 21%

---

# Identifiant visiteur Experience Cloud

La dimension « Identifiant visiteur Experience Cloud »[&#x200B; fournit l’Experience Cloud ID (ECID](overview.md) pour chaque visiteur. Il s’agit d’un nombre de 128 bits composé de deux nombres concaténés de 64 bits ajoutés à 19 chiffres.

>[!IMPORTANT]
>
>Cette dimension est uniquement disponible dans Data Warehouse.

## Renseignement de cette dimension avec des données

Cette dimension nécessite une implémentation qui utilise le service Experience Cloud ID (ECID). Il correspond à la colonne `mcvisid` dans les flux de données. Voir [Référence des colonnes de données](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) pour plus d’informations.

## Éléments de dimension

Les éléments Dimension incluent l’Experience Cloud ID de chaque visiteur.
