---
title: Evénement achat
description: Utilisez le d’achat pour collecter des données pour les mesures "Commandes", "Unités" et "Recettes".
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Evénement achat

Le  d’achat est une valeur de la `events` variable. Cette valeur est utile pour les entreprises qui souhaitent collecter des données sur les recettes générées par leur site. Elle dépend fortement des [`products`](../products.md) variables et [`purchaseID`](../purchaseid.md) des variables.

Lorsque vous définissez un  d’achat, il affecte les mesures suivantes :

* La mesure Commandes est incrémentée de 1
* La mesure &quot;Unités&quot; est incrémentée en fonction du nombre de produits dans la `products` variable
* La mesure &quot;Recettes&quot; augmente de la somme des paramètres de prix dans la `products` variable

## Définition du  d’achat dans Adobe Experience Platform Launch

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Rules] onglet, puis cliquez sur la règle souhaitée (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une [!UICONTROL Adobe Analytics - Set Variables] action existante ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la [!UICONTROL Extension] liste déroulante sur Adobe Analytics et la [!UICONTROL Action Type] sur [!UICONTROL Set Variables].
6. Localisez la [!UICONTROL Events] section et définissez la liste déroulante des  sur [!UICONTROL purchase].

D’autres variables dépendantes, telles que `products` et `purchaseID` n’ont pas de champs dédiés dans Launch. Utilisez l’éditeur de code personnalisé suivant la syntaxe AppMeasurement pour ces variables.

## Définition du  d’achat dans AppMeasurement et lancement de l’éditeur de code personnalisé

Le  d’achat est une chaîne définie dans le cadre de la variable .

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## Achat  déduplication

Lorsque vous déclenchez un  d’achat, Adobe vérifie les éléments suivants :

* L’accès contient-il la `purchaseID` variable ? Dans le cas contraire, Adobe utilise les informations de l’accès pour créer un &quot;ID d’achat temporaire&quot;. Cet ID d’achat temporaire s’applique uniquement au de l’accès. Les 5 identifiants d’achat temporaires précédents sont stockés pour chaque identifiant de par suite de rapports.
* L’ID d’achat temporaire correspond-il à l’un des cinq derniers ID d’achat temporaire stockés ? Si tel est le cas, la demande d’image est considérée comme un achat en double. Aucune variable de conversion, y compris l’événement d’achat, ne figure dans les rapports.
* Si la `purchaseID` variable est définie, correspond-elle à une valeur déjà collectée dans la suite de rapports dans tous les ? Si tel est le cas, la demande d’image est considérée comme un achat en double. Aucune variable de conversion, y compris l’événement d’achat, ne figure dans les rapports.
