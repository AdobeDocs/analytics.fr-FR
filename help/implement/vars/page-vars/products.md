---
title: products
description: Envoyez des données autour du ou des produits affichés ou dans le panier.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# products

La `products` variable effectue le suivi des produits et des propriétés qui leur sont liées. Cette variable est généralement définie sur des pages de produit individuelles, des pages de panier d’achat et des pages de confirmation d’achat. Il s’agit d’une variable à plusieurs valeurs, ce qui signifie que vous pouvez envoyer plusieurs produits dans le même accès et qu’Adobe analyse la valeur dans des valeurs de dimension distinctes.

> [!NOTE] Si cette variable est définie dans un accès sans de panier d’achat dans la [`events`](events/events-overview.md) variable, la mesure &quot;de produits &quot; est incrémentée de 1. Veillez à définir le de panier approprié pour chaque accès.

## Produits dans Adobe Experience Platform Launch

Il n&#39;existe pas de champ dédié dans Launch pour définir cette variable ; toutefois, il existe plusieurs extensions tierces pour vous aider.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Extensions] onglet, puis cliquez sur [!UICONTROL Catalog] pour afficher toutes les extensions disponibles.
4. Recherchez le terme &quot;produit&quot;, qui révèle plusieurs extensions disponibles pour aider à définir cette variable.

Vous pouvez utiliser l’une de ces extensions ou l’éditeur de code personnalisé suivant la syntaxe AppMeasurement ci-dessous.

## s.products dans AppMeasurement et Lancement de l’éditeur de code personnalisé

La `s.products` variable est une chaîne qui contient plusieurs champs délimités par produit. Chaque produit peut contenir jusqu’à 100 octets dans tous les champs. Délimitez chaque champ par un point-virgule (`;`) dans la chaîne.

* **** de (facultatif) : Le de produit global . Votre organisation décide de regrouper les produits dans des .
* **Nom** du produit (obligatoire) : Nom du produit.
* **Quantité** (facultatif) : Combien de ce produit se trouve dans le panier ? Ce champ s’applique uniquement aux accès avec le  d’achat.
* **Prix** (facultatif) : Prix total du produit sous forme de décimale. Si la quantité est supérieure à un, définissez le prix sur le total et non sur le prix du produit individuel. Aligne la devise de cette valeur pour qu’elle corresponde à la [`currencyCode`](../config-vars/currencycode.md) variable. N’incluez pas le symbole de devise dans ce champ. Ce champ s’applique uniquement aux accès avec le  d’achat.
* **** de (facultatif) :  lié au produit. Délimitez plusieurs  avec un tuyau (`|`). Voir  [](events/events-overview.md) pour plus d’informations.
* **eVars** (facultatif) : eVars de marchandisage liées au produit. Délimitez plusieurs eVars de marchandisage à l’aide d’une barre verticale (`|`). Voir eVars [de](../../../components/c-variables/c-merch-variables/var-merchandising.md) marchandisage pour en savoir plus.

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

Cette variable prend en charge plusieurs produits dans le même accès. Il est utile pour le panier et les achats contenant plusieurs produits. Bien qu’il existe une limite de 100 octets par produit, la longueur totale de la `products` variable est de 64 Ko. Séparez chaque produit par une virgule (`,`) dans la chaîne.

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2,1,5.99";
```

> [!IMPORTANT] Supprimez tous les points-virgules, virgules et tuyaux des noms de produits, des  de et des valeurs d’eVar de marchandisage. Si le nom d’un produit comporte une virgule, AppMeasurement l’analyse comme le  d’un nouveau produit. Cette analyse incorrecte renvoie le reste de la chaîne du produit, provoquant des données incorrectes dans les dimensions et les rapports.

## Exemples

La `products` variable est flexible lorsque vous omettez des champs et incluez plusieurs produits. Cette souplesse peut faciliter l’absence d’un délimiteur, ce qui entraîne l’envoi de données incorrectes à Adobe par votre implémentation.

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name if you do not want to use product category
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product,;Example product";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = "Example category;Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = "Example category;Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = "Example category 1;Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = "Example category;Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = "Example category;Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```
