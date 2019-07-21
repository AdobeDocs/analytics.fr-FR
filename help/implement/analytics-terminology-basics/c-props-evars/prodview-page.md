---
description: La variable products sert à effectuer le suivi des produits et des catégories de produits (ainsi que de la quantité achetée et du prix d’achat).
keywords: Implémentation d'Analytics ; variable products ; consultation du produit ; événement de réussite
seo-description: La variable products sert à effectuer le suivi des produits et des catégories de produits (ainsi que de la quantité achetée et du prix d’achat).
seo-title: Page d'affichage détaillée du produit
solution: Analytics
title: Page d'affichage détaillée du produit
topic: Développeur et mise en œuvre
uuid: 464 c 9 daf-b 042-4 fb 8-8 ca 6-e 104 c 0 bcef 45
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Page d'affichage détaillée du produit

La variable products sert à effectuer le suivi des produits et des catégories de produits (ainsi que de la quantité achetée et du prix d’achat).

A success event should always be set in conjunction with the *`products`* variable.

```js
s.events="prodView"
```

>[!NOTE]
>
>While *`prodView`* is treated in implementation like an event, it does not have the same flexibility in the interface. The *`prodView`*event is an instance of the product and is only available in the *`products`* report. vous conseille d’utiliser un événement *`custom`* en plus de l’événement *`prodView`.* Cela vous permet d’afficher les mesures de consultation des produits aux côtés d’autres mesures dans d’autres rapports de conversion.

```js
s.products=";diamond earrings (54321)"
```

>[!NOTE]
>
>La syntaxe de chaîne de produits doit commencer par un point-virgule. Il s’agit d’un élément hérité. Auparavant, il servait à délimiter la catégorie et le produit. Cependant, cela crée une limite dans l’interface si vous souhaitez modifier la méthode de classification des produits. Pour bénéficier d’un maximum de souplesse dans le cadre de la génération de rapports, il est préférable de ne rien indiquer et d’utiliser Classifications afin de configurer des catégories.

## Page de panier d’achats (scOpen, scAdd, scRemove ) {#section_469B64F4150149DFB6B2C731279C0BC7}

```js
s.events="scOpen,scAdd" 
s.products=";SKU" 
```

## Page du premier passage en caisse {#section_E15607A9AECB44F79631926C853CF64E}

```js
s.events="scCheckout" 
s.products=”;SKU" 
```

## Page de confirmation {#section_E006943CD5FD42358086581CA44B9660}

```js
s.events="purchase" 
s.products=";SKU" 
```

>[!NOTE]
>
>While using the SKU in the product string may make the *`products`* report less readable, it provides the maximum flexibility later when you want to classify your products. Vous pouvez créer des catégories à partir du SKU indiquant la finition, le fabricant, la catégorie et la sous-catégorie.

Lorsque la variable *`products`* est définie avec l’événement *`purchase`, la quantité achetée et le prix d’achat total sont inclus dans la valeur « products », comme indiqué ci-dessus.*
