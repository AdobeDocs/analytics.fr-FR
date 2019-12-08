---
description: La variable products sert à effectuer le suivi des produits et des catégories de produits (ainsi que de la quantité achetée et du prix d’achat).
keywords: Analytics Implementation;products variable;product view;success event
title: Page Affichage du produit détaillé
topic: Developer and implementation
uuid: 464c9daf-b042-4fb8-8ca6-e104c0bcef45
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Page Affichage du produit détaillé

La variable products sert à effectuer le suivi des produits et des catégories de produits (ainsi que de la quantité achetée et du prix d’achat).

Un événement de succès doit toujours être défini conjointement avec la variable *`products`*.

```js
s.events="prodView"
```

> [!NOTE] Bien que l’événement *`prodView`* soit traité comme un événement dans le cadre de la mise en œuvre, il ne bénéficie pas de la même souplesse dans l’interface. L’événement *`prodView`* est une instance du produit, disponible uniquement dans le rapport *`products`*. vous conseille d’utiliser un événement *`custom`* en plus de l’événement *`prodView`*. Cela vous permet d’afficher les mesures de consultation des produits aux côtés d’autres mesures dans d’autres rapports de conversion.

```js
s.products=";diamond earrings (54321)"
```

> [!NOTE] La syntaxe de la chaîne « products » doit commencer par un point-virgule. Il s’agit d’un élément hérité. Auparavant, il servait à délimiter la catégorie et le produit. Cependant, cela crée une limite dans l’interface si vous souhaitez modifier la méthode de classification des produits. Pour bénéficier d’un maximum de souplesse dans le cadre de la génération de rapports, il est préférable de ne rien indiquer et d’utiliser Classifications afin de configurer des catégories.

## Page de panier d’achats (scOpen, scAdd, scRemove ) {#section_469B64F4150149DFB6B2C731279C0BC7}

```js
s.events="scOpen,scAdd"
s.products=";SKU"
```

## Page du premier passage en caisse {#section_E15607A9AECB44F79631926C853CF64E}

```js
s.events="scCheckout"
s.products=";SKU"
```

## Page de confirmation {#section_E006943CD5FD42358086581CA44B9660}

```js
s.events="purchase"
s.products=";SKU"
```

> [!NOTE] Bien que l’utilisation du SKU dans la chaîne du produit puisse rendre le rapport *`products`* moins lisible, elle offre une flexibilité maximale ultérieurement lorsque vous souhaitez classer vos produits. Vous pouvez créer des catégories à partir du SKU indiquant la finition, le fabricant, la catégorie et la sous-catégorie.

Lorsque la variable *`products`* est définie avec l’événement *`purchase`*, la quantité achetée et le prix d’achat total sont inclus dans la valeur « products », comme indiqué ci-dessus.
