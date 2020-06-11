---
title: eVar (marchandisage)
description: Variables personnalisées liées à des produits individuels.
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 29%

---


# eVar (marchandisage)

*Cette page d’aide décrit comment implémenter des eVars de marchandisage. Pour plus d’informations sur le fonctionnement des eVars de marchandisage en tant que dimension, voir[eVars (marchandisage)](/help/components/dimensions/evar-merchandising.md)dans le guide de l’utilisateur Composants.*

## Configurer des eVars dans les paramètres de la suite de rapports

Avant d’utiliser des eVars dans votre implémentation, veillez à configurer l’eVar selon la syntaxe souhaitée dans les paramètres de la suite de rapports. Reportez-vous à la section [Variables de conversion](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) dans le guide Administrateur.

>[!IMPORTANT] Si les eVars de marchandisage ne sont pas correctement configurées, des valeurs inattendues ou des données perdues sont perdues pour la variable. Assurez-vous qu’il est correctement configuré pour votre mise en oeuvre.

## Mise en oeuvre à l’aide de la syntaxe du produit

When &#39;Product Syntax&#39; is enabled, the merchandising category is populated directly within the `products` variable, so selecting and setting a binding event is not required. Il est vivement conseillé d’utiliser cette méthode, à moins que la valeur ne soit pas disponible pour être définie dans la variable `products` lorsque l’événement de succès se produit.

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

The value for `eVar1` is assigned to the product. Tous les événements de réussite suivants qui impliquent ce produit sont crédités à la valeur eVar.

## Implémentation à l’aide de la syntaxe de variable de conversion

Conversion Variable Syntax is used when the eVar value is not available to set in the `products` variable. Ce scénario signifie généralement que votre page n’a aucun contexte dans le canal de marchandisage ou la méthode de recherche. Dans ce cas, vous définissez la variable de marchandisage avant d’arriver à la page du produit et la valeur persiste jusqu’à ce que le événement de liaison se produise.

Lorsque l’événement de liaison sélectionné en cours de configuration se produit, la valeur persistante de l’eVar est associée au produit. For example, if `prodView` is specified as the binding event, the merchandising category is tied to the current product list only at the time the event occurs. Seuls les événements de liaison ultérieurs pourront mettre à jour une eVar de marchandisage qui a déjà été affectée à un produit.

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = "Birds;Canary";
```

The value `"Aviary"` for `eVar1` is assigned to the product `"Canary"`. Tous les événements de réussite ultérieurs qui impliquent ce produit sont crédités à `"Canary"`. De plus, la valeur actuelle de la variable de marchandisage sera liée à tous les produits ultérieurs, jusqu’à ce que l’une des conditions suivantes soit remplie :

* L&#39;eVar arrive à expiration (selon le paramètre &quot;Expire après&quot;).
* L’eVar de marchandisage est remplacée par une nouvelle valeur.
