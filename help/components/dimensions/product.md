---
title: Product
description: Nom du produit.
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '142'
ht-degree: 100%

---

# Product

La dimension « Produit » indique le nom du produit dans l’accès. Elle est utile pour les implémentations qui utilisent la variable `products` et cherchent à obtenir des mesures liées aux produits, comme les articles les plus vendus ou les plus consultés. Il est possible que cette dimension reste délibérément vide si votre site ne contient aucun produit.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à la deuxième partie de la chaîne dans la variable [`products`](/help/implement/vars/page-vars/products.md). Les caractères entre le premier et le deuxième point-virgule (`;`) renseignent cette dimension.

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée de votre implémentation, votre entreprise détermine les éléments de dimension. Adobe recommande d’établir une convention d’affectation des noms cohérente pour les produits. Des [classifications](../classifications/c-classifications.md) sont disponibles si vous souhaitez regrouper les produits différemment ou fournir un nom plus convivial. Adobe recommande d’utiliser les dimensions « Produit » et « Catégorie ».
