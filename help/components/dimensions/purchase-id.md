---
title: Identifiant d’achat
description: Identifiant unique d’un achat, disponible dans Data Warehouse.
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
source-wordcount: '124'
ht-degree: 18%
---
# Identifiant d’achat

La [dimension](overview.md) « ID d’achat » fournit l’identifiant unique d’un achat.

>[!IMPORTANT]
>
>Cette dimension est uniquement disponible dans Data Warehouse.

## Renseignement de cette dimension avec des données

Cette dimension est définie à l’aide de la variable [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) . Il correspond à la colonne `purchaseid` dans les flux de données. Voir [Référence des colonnes de données](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) pour plus d’informations.

| Propriété | Valeur |
| --- | --- |
| **Variable** | [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) |
| **Champ Web SDK/XDM** | [`commerce.order.purchaseID`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details) |
| **Paramètre de requête** | [`purchaseID`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<purchaseId>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | 20 octets |
| **Persistance** | Hit |

## Éléments de dimension

Les éléments Dimension incluent les identifiants d’achat collectés sur votre site.
