---
title: Catégorie
description: La catégorie de produits de l’accès.
feature: Dimensions
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
TQID: https://experienceleague.adobe.com/3G1qDbtVnRj8At-FU1fNaI8KLboMQvo8NKktinrTbs8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 155
ht-degree: 93%

---

# Catégorie

La [dimension](overview.md) « Catégorie » indique la catégorie de produits de l’accès. Elle est utile pour les implémentations qui utilisent la variable `products` et cherchent à obtenir des mesures de catégorie de produits, comme les articles les plus vendus ou les plus consultés. Il est possible que cette dimension reste délibérément vide si votre site ne contient aucun produit.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à la première partie de la chaîne dans la variable [`products`](/help/implement/vars/page-vars/products.md). Tout ce qui précède le premier point-virgule (`;`) renseigne cette dimension.

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée de votre implémentation, votre entreprise détermine les éléments de dimension. Adobe recommande de regrouper des produits individuels en catégories significatives, en utilisant à la fois les dimensions « Produit » et « Catégorie ».

>[!TIP]
>
>Dans les versions précédentes d’Adobe Analytics, certaines limites à la dimension « Catégorie » étaient imposées en raison de son architecture de traitement. Ces limites ont depuis été supprimées, ce qui vous permet d’utiliser n’importe quelle mesure et n’importe quelle répartition.
