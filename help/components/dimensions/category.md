---
title: Catégorie
description: catégorie de produit de l’accès.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 1%

---


# Catégorie

La dimension &quot;Catégorie&quot; rapporte la catégorie de produit de l’accès. Il est utile pour les implémentations qui utilisent la `products` variable et souhaitent afficher les mesures autour de la catégorie de produits, telles que les meilleurs vendeurs ou les plus consultés. Cette dimension peut être volontairement vide si vous n’avez aucun produit sur votre site.

## Renseigner cette dimension avec des données

Cette dimension fait référence à la première partie de la chaîne dans la [`products`](/help/implement/vars/page-vars/products.md) variable. Tout ce qui précède le premier point-virgule (`;`) renseigne cette dimension.

## Valeurs de dimension

Cette variable étant basée sur une chaîne personnalisée dans votre implémentation, votre organisation détermine les valeurs de dimension. Adobe recommande de regrouper des produits individuels en catégories significatives, en utilisant à la fois les dimensions &quot;Produit&quot; et &quot;Catégorie&quot;.

>[!TIP]
>
>Dans les versions précédentes d&#39;Adobe Analytics, certaines limites à la dimension &quot;Catégorie&quot; ont été imposées en raison de son architecture de traitement. Ces limites ont été supprimées depuis, ce qui vous permet d’utiliser n’importe quelle mesure et toute ventilation.
