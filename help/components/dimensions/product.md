---
title: Product
description: Nom du produit.
translation-type: tm+mt
source-git-commit: bddfc52d460e87a70e7cff149f197570f405037a
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---


# Product

La dimension &quot;Produit&quot; rapporte le nom du produit dans l’accès. Il est utile pour les implémentations qui utilisent la `products` variable et souhaitent afficher des mesures autour des produits, tels que les meilleurs vendeurs ou les plus consultés. Cette dimension peut être volontairement vide si vous n’avez aucun produit sur votre site.

## Renseigner cette dimension avec des données

Cette dimension fait référence à la deuxième partie de la chaîne dans la [`products`](/help/implement/vars/page-vars/products.md) variable. Les caractères entre le premier et le deuxième point-virgule (`;`) renseignent cette dimension.

## Valeurs de dimension

Cette variable étant basée sur une chaîne personnalisée dans votre implémentation, votre organisation détermine les valeurs de dimension. Adobe recommande d’établir une convention d’affectation de nom cohérente pour les produits. [Les classifications](../c-classifications2/c-classifications.md) sont disponibles si vous souhaitez regrouper les produits différemment ou fournir un nom plus convivial. Adobe recommande d&#39;utiliser les dimensions &quot;Produit&quot; et &quot;Catégorie&quot;.
