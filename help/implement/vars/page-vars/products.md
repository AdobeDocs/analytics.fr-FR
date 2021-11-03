---
title: products
description: Permet d’envoyer des données concernant le ou les produits affichés ou du panier.
exl-id: f26e7c93-f0f1-470e-a7e5-0e310ec666c7
source-git-commit: b78604e675a371894b1839d1751d44a1e8b2c5c1
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 93%

---

# products

La variable `products` effectue le suivi des produits et des propriétés qui leur sont liées. Cette variable est généralement définie sur des pages de produit individuelles, des pages de panier d’achat et des pages de confirmation d’achat. Il s’agit d’une variable à plusieurs valeurs, ce qui signifie que vous pouvez envoyer plusieurs produits dans le même accès et qu’Adobe analyse la valeur dans des éléments de dimension distincts.

>[!NOTE]
>
>Si cette variable est définie dans un accès sans variable [`events`](events/events-overview.md), la mesure [Consultations produits](/help/components/metrics/product-views.md) est incrémentée de 1. Assurez-vous de définir les événements appropriés pour chaque accès avec la variable `products`.

## Variable products à laide de balises dans Adobe Experience Platform

Il n’existe pas de champ dédié dans l’interface utilisateur de la collecte de données pour définir cette variable. Toutefois, il existe plusieurs extensions tierces pour vous aider.

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur [!UICONTROL Catalogue] pour afficher toutes les extensions disponibles.
4. Recherchez le terme « produit », qui révèle plusieurs extensions disponibles pour aider à définir cette variable.

Vous pouvez utiliser l’une de ces extensions ou l’éditeur de code personnalisé en respectant la syntaxe AppMeasurement ci-dessous.

## s.products dans AppMeasurement et l’éditeur de code personnalisé

La variable `s.products` est une chaîne qui contient plusieurs champs délimités par produit. Délimitez chaque champ par un point-virgule (`;`) dans la chaîne.

>[!IMPORTANT]
>**[!UICONTROL Catégorie ]**n’est plus recommandée comme option viable pour effectuer le suivi des performances des catégories de produits. Par conséquent, toutes les chaînes de produit doivent commencer par le point-virgule, ce qui signifie que le premier champ est vide.

* **Nom du produit** (obligatoire) : nom du produit. La longueur maximale de ce champ est de 100 octets.
* **Quantité** (facultatif) : quantité de ce produit dans le panier ? Ce champ s’applique uniquement aux accès avec l’événement d’achat.
* **Prix** (facultatif) : prix total du produit sous forme de décimale. Si la quantité est supérieure à un, définissez le prix sur le total et non sur le prix du produit individuel. Alignez la devise de cette valeur pour qu’elle corresponde à la variable [`currencyCode`](../config-vars/currencycode.md). N’incluez pas le symbole de devise dans ce champ. Ce champ s’applique uniquement aux accès avec l’événement d’achat.
* **Événements** (facultatif) : événements liés au produit. Délimitez plusieurs événements à l’aide d’une barre verticale (`|`). Voir [Événements](events/events-overview.md) pour plus d’informations.
* **eVars** (facultatif) : eVars de marchandisage liées au produit. Délimitez plusieurs eVars de marchandisage à l’aide d’une barre verticale (`|`). Voir [eVars de marchandisage](evar-merchandising.md) pour en savoir plus.

```js
// Set a single product using all available fields
s.products = ";Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

Cette variable prend en charge plusieurs produits dans le même accès. Celle-ci est utile pour le panier et les achats contenant plusieurs produits. La longueur maximale de la chaîne `products` complète est de 64 Ko. Séparez chaque produit par une virgule (`,`) dans la chaîne.

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = ";Example product 1;1;3.50,Example category 2;Example product 2;1;5.99";
```

>[!IMPORTANT]
>
>Supprimez tous les points-virgules, virgules et tuyaux des noms de produits, des catégories et des valeurs d’eVar de marchandisage. Si un nom de produit comporte une virgule, AppMeasurement l’analyse comme le début d’un nouveau produit. Cette analyse incorrecte renvoie le reste de la chaîne du produit, provoquant des données incorrectes dans les dimensions et les rapports.

## Exemples

La variable `products` est flexible lorsque vous omettez des champs et incluez plusieurs produits. Cette souplesse peut faciliter l’absence d’un délimiteur, ce qui entraîne l’envoi de données incorrectes à Adobe par votre mise en œuvre.

```js
// Include only product and category. Common on individual product pages
s.products = ";Example product";

// Include only product name
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = ";Example product 1,;Example product 2";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = ";Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = ";Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = ";Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = ";Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = ";Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = ";Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```

Si vous utilisez la `digitalData` [couche de données](../../prepare/data-layer.md), vous pouvez effectuer une itération dans le tableau d’objets `digitalData.product` :

```js
for(var i = 0; i < digitalData.product.length; i++) {
    // Add individual product info to the product string
    s.products += digitalData.product[i].category.primaryCategory + ";" + digitalData.product[i].productInfo.productName;
    // If there are more products, add a comma
    if(i != digitalData.product.length - 1) {
        s.products += ",";
    }
}
```
