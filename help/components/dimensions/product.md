---
title: Product
description: Nom du produit.
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
TQID: https://experienceleague.adobe.com/SMFFeSTkQyQoSWNFc8qHJRxYkJQmiJoKd0v4rS6xRKc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 58%
---
# Product

La [dimension](overview.md) « Produit » indique le nom du produit dans l’accès. Elle est utile pour les implémentations qui utilisent la variable `products` et cherchent à obtenir des mesures liées aux produits, comme les articles les plus vendus ou les plus consultés. Il est possible que cette dimension reste délibérément vide si votre site ne contient aucun produit.

## Renseignement de cette dimension avec des données

Cette dimension fait référence au nom du produit dans la variable [`products`](/help/implement/vars/page-vars/products.md), qui correspond à la chaîne entre le premier et le deuxième point-virgule (`;`).

| Propriété | Valeur |
| --- | --- |
| **Variable** | [`products`](/help/implement/vars/page-vars/products.md) |
| **Champ Web SDK/XDM** | [`productListItems[].name`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details) |
| **Paramètre de requête** | [`products`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<products>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | 100 octets |
| **Persistance** | Hit |

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée dans votre mise en œuvre, votre entreprise détermine quels sont les éléments de dimension. Adobe recommande d’établir une convention de nommage cohérente pour les produits. Des [classifications](../classifications/classifications-overview.md) sont disponibles si vous souhaitez regrouper les produits différemment ou fournir un nom plus convivial. Adobe recommande d’utiliser les dimensions « Produit » et « Catégorie ».
