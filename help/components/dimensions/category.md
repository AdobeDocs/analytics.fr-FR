---
title: Catégorie
description: La catégorie de produits du hit.
feature: Dimensions
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
TQID: 'https://experienceleague.adobe.com/3G1qDbtVnRj8At-FU1fNaI8KLboMQvo8NKktinrTbs8'
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
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
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
source-wordcount: '203'
ht-degree: 63%
---
# Catégorie

La [dimension](overview.md) « Catégorie » indique la catégorie de produits de l’accès. Elle est utile pour les implémentations qui utilisent la variable `products` et cherchent à obtenir des mesures de catégorie de produits, comme les articles les plus vendus ou les plus consultés. Il est possible que cette dimension reste délibérément vide si votre site ne contient aucun produit.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à la catégorie de produits dans la variable [`products`](/help/implement/vars/page-vars/products.md), c’est-à-dire tout ce qui précède le premier point-virgule (`;`).

| Propriété | Valeur |
| --- | --- |
| **Variable** | [`products`](/help/implement/vars/page-vars/products.md) |
| **Champ Web SDK/XDM** | [`productListItems[].productCategories[].categoryID`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details) |
| **Paramètre de requête** | [`products`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<products>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | 100 octets |
| **Persistance** | Hit |

## Éléments de dimension

Comme cette variable repose sur une chaîne personnalisée de votre mise en œuvre, votre organisation détermine les éléments de dimension. Adobe recommande de regrouper des produits individuels en catégories significatives, en utilisant à la fois les dimensions « Produit » et « Catégorie ».

>[!TIP]
>
>Dans les versions précédentes d’Adobe Analytics, certaines limites à la dimension « Catégorie » étaient imposées en raison de son architecture de traitement. Ces limites ont depuis été supprimées, ce qui vous permet d’utiliser n’importe quelle mesure et n’importe quelle répartition.
