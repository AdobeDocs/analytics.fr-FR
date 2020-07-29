---
title: Product
description: Nom du produit.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---


# Product

La dimension &quot;Produit&quot; rapporte le nom du produit dans l’accès. Il est utile pour les implémentations qui utilisent la `products` variable et souhaitent afficher des mesures autour des produits, tels que les meilleurs vendeurs ou les plus consultés. Cette dimension peut être volontairement vide si vous n’avez aucun produit sur votre site.

## Renseigner cette dimension avec des données

Cette dimension fait référence à la deuxième partie de la chaîne dans la [`products`](/help/implement/vars/page-vars/products.md) variable. Les caractères entre le premier et le deuxième point-virgule (`;`) renseignent cette dimension.

## Éléments de Dimension

Cette variable étant basée sur une chaîne personnalisée dans votre implémentation, votre organisation détermine les éléments de dimension. Adobe vous recommande d’établir une convention d’affectation de nom cohérente pour les produits. [Les classifications](../classifications/c-classifications.md) sont disponibles si vous souhaitez regrouper les produits différemment ou fournir un nom plus convivial. Adobe recommande d&#39;utiliser les dimensions &quot;Produit&quot; et &quot;Catégorie&quot;.
