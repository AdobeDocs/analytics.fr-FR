---
title: Identifiant visiteur
description: Identifiant unique d’un visiteur ou d’une visiteuse, disponible dans Data Warehouse.
feature: Dimensions
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 18%
---
# Identifiant visiteur

La [dimension](overview.md) « Identifiant visiteur » fournit l’identifiant unique de chaque visiteur.

>[!IMPORTANT]
>
>Cette dimension est uniquement disponible dans Data Warehouse.

## Renseignement de cette dimension avec des données

Adobe génère automatiquement un identifiant visiteur pour chaque visiteur. Cette valeur est identique à la valeur concaténée des colonnes `visid_high` et `visid_low` dans les flux de données. Vous pouvez remplacer la valeur générée automatiquement par la variable `visitorID`. Voir [Référence des colonnes de données](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) pour plus d’informations.

| Propriété | Valeur |
| --- | --- |
| **Variable** | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) |
| **Champ Web SDK/XDM** | Aucun |
| **Paramètre de requête** | [`vid`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<visitorId>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | 255 octets |
| **Persistance** | S.O. |

## Éléments de dimension

Les éléments Dimension incluent l’identifiant unique de chaque visiteur.
