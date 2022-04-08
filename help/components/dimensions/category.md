---
title: Catégorie
description: La catégorie de produits de l’accès.
feature: Dimensions
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '155'
ht-degree: 100%

---

# Catégorie

La dimension « Catégorie » indique la catégorie de produits de l’accès. Elle est utile pour les implémentations qui utilisent la variable `products` et cherchent à obtenir des mesures de catégorie de produits, comme les articles les plus vendus ou les plus consultés. Il est possible que cette dimension reste délibérément vide si votre site ne contient aucun produit.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à la première partie de la chaîne dans la variable [`products`](/help/implement/vars/page-vars/products.md). Tout ce qui précède le premier point-virgule (`;`) renseigne cette dimension.

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée de votre implémentation, votre entreprise détermine les éléments de dimension. Adobe recommande de regrouper des produits individuels en catégories significatives, en utilisant à la fois les dimensions « Produit » et « Catégorie ».

>[!TIP]
>
>Dans les versions précédentes d’Adobe Analytics, certaines limites à la dimension « Catégorie » étaient imposées en raison de son architecture de traitement. Ces limites ont depuis été supprimées, ce qui vous permet d’utiliser n’importe quelle mesure et n’importe quelle ventilation.
