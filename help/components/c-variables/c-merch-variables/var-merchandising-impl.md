---
description: Description de l’activation et de l’implémentation d’une variable de marchandisage.
keywords: Analytics Implementation;merchandising;variable;product syntax;Conversion Variable Syntax;s.products
solution: Analytics
title: Implémentation d’une variable de marchandisage
topic: Developer and implementation
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Implémentation d’une variable de marchandisage

Description de l’activation et de l’implémentation d’une variable de marchandisage.

## Activation d’une variable de marchandisage

Le marchandisage peut être activé pour toute eVar personnalisée sous Outils **[!UICONTROL d’]** administration &gt; Suites **[!UICONTROL de]** rapports &gt; Variables **[!UICONTROL de]** conversion.

![](assets/merch-enable.png)

| Paramètre | Description |
|--- |--- |
| Expire après | Définit la durée de vie des valeurs de marchandisage. |
| Marchandisage | **** Syntaxe du produit : La valeur est définie dans `s.products`.<br>**** Syntaxe de la variable de conversion : La valeur est définie dans l’eVar de marchandisage désignée. |
| Evénement de liaison de marchandisage (Syntaxe de la variable de conversion uniquement) | Indique à quel moment un produit doit être lié à la catégorie de marchandisage actuelle. Vous pouvez sélectionner plusieurs événements en maintenant la touche Ctrl enfoncée et en cliquant sur plusieurs éléments de la liste. Vous ne pouvez sélectionner un élément que lorsque le paramètre « Syntaxe de la variable de conversion » est actif. |

## Implémentation à l’aide de la syntaxe du produit

Lorsque le paramètre Syntaxe du produit est activé, la catégorie de marchandisage est directement remplie dans la variable products. La sélection et la définition d’un événement de liaison ne sont donc pas requises. Il est vivement conseillé d’utiliser cette méthode, à moins que la valeur ne soit pas disponible pour être définie dans la variable `s.products` lorsque l’événement de succès se produit.

### du lien personnalisé

```js
s.products="category;product;quantity;price;event_incrementer;eVarN=merch_category|eVarM=merch_category2";
```

### Exemple

```js
s.events="prodView";
s.products=";Snow Goggles;;;;eVar1=goggles";
```

La valeur "lunettes de ski" pour eVar1 est affectée au produit "Lunettes de neige". Tous les événements de succès ultérieurs (ajouts de produits, passages en caisse, achats, etc.) qui concernent ce produit seront crédités à « lunettes de ski » (goggles).

## Implémentation à l’aide de la variable de syntaxe de conversion

La variable de syntaxe de conversion doit être utilisée lorsque la valeur eVar n’est pas disponible pour être définie dans `s.products`. Cela signifie généralement que votre page n’est pas en mesure de déterminer le canal de marchandisage ou la méthode de recherche. Dans ce cas, vous devez définir la valeur de marchandisage avant d’arriver à la page du produit et la valeur persiste jusqu’à l’événement de liaison.

Lorsque l’événement de liaison sélectionné en cours de configuration se produit, la valeur persistante de l’eVar est associée au produit. Par exemple, si prodView est spécifié en tant qu’événement de liaison, la catégorie de marchandisage n’est liée à la liste des produits en cours qu’au moment où l’événement se produit. Seuls les événements de liaison ultérieurs pourront mettre à jour une eVar de marchandisage qui a déjà été affectée à un produit.

### du lien personnalisé

Placez-le sur la même page ou sur la page précédente avant l’événement de liaison :

```js
s.eVar1="merchandising_category";
```

Placez le curseur sur la page où survient l’événement de liaison :

```js
s.events="prodView";
s.products="category;product";
```

### Exemple

Page 1 de la visite :

```js
s.eVar1="Outdoors"
```

Page 2 de la visite :

```js
s.events="prodView";
s.products=";Snow Goggles";
```

La valeur "Extérieur" pour eVar1 est affectée au produit "Lunettes de neige". Tous les événements de réussite suivants (ajouts de produit, passages en caisse, achats, etc.) qui impliquent ce produit sont crédités à "Lunettes de neige". De plus, la valeur actuelle de la variable de marchandisage sera liée à tous les produits ultérieurs, jusqu’à ce que l’une des conditions suivantes soit remplie :

* Expiration de l’eVar (sur la base du paramètre « Expire après »)
* L’eVar de marchandisage est remplacée par une nouvelle valeur.

## Informations supplémentaires externes

[Marchandisage](https://analyticsdemystified.com/adobe-analytics/advanced-conversion-syntax-merchandising/) avancé de la syntaxe de conversion sur [!DNL analyticsdemystified.com]
