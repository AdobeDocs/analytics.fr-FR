---
title: Événement d’achat
description: Utilisez l’événement d’achat pour collecter des données pour les mesures Commandes, Unités et Recettes.
feature: Variables
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
role: Admin, Developer
source-git-commit: 7c8ffe8f4ccf0577136e4d7ee96340224897d2a4
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 70%

---

# Événement d’achat

L’événement d’achat est une valeur de la variable `events`. Cette valeur est utile pour les entreprises qui souhaitent collecter des données sur les recettes générées par leur site. Elle dépend fortement des variables [`products`](../products.md) et [`purchaseID`](../purchaseid.md).

Lorsque vous définissez un événement d’achat, celui-ci affecte les mesures suivantes :

* La mesure Commandes est incrémentée de 1
* La mesure Unités est incrémentée en fonction du nombre de produits dans la variable `products`
* La mesure Recettes augmente de la somme des paramètres de prix dans la variable `products`

>[!NOTE]
>
>Le chiffre d’affaires n’est pas multiplié par le champ de quantité. Par exemple, `s.products="Womens;Socks;5;4.50"` ne transmet pas 22,50 $ au chiffre d’affaires, mais 4,50 $. Assurez-vous que votre mise en oeuvre transmet le total des recettes pour la quantité répertoriée. Par exemple : `s.products="Womens;Socks;5;22.50"`.

## Définir l’événement d’achat à l’aide du SDK Web

Si vous utilisez l’ [**objet XDM**](/help/implement/aep-edge/xdm-var-mapping.md), l’événement d’achat utilise les champs XDM suivants :

* Les commandes sont mappées à `xdm.commerce.purchases.value`.
* Les unités sont mappées à la somme de tous les champs `xdm.productListItems[].quantity`. Voir [`products`](../products.md) pour plus d’informations.
* Le chiffre d’affaires est mappé à la somme de tous les champs `xdm.productListItems[].priceTotal`.

```json
{
  "xdm": {
    "commerce": {
      "purchases": {
        "value": 1
      }
    }
  }
}
```

Si vous utilisez l’ [**objet de données**](/help/implement/aep-edge/data-var-mapping.md), l’événement d’achat utilise `data.__adobe.analytics.events`, selon la syntaxe de chaîne d’AppMeasurement.

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "events": "purchase"
      }
    }
  }
}
```

## Définir l’événement d’achat à l’aide de l’extension Adobe Analytics

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL Type d’action] sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Events] et définissez la liste déroulante [!UICONTROL Events] sur [!UICONTROL purchase].

D’autres variables dépendantes, telles que `products` et `purchaseID`, n’ont pas de champs dédiés dans l’extension Analytics au sein de la collecte de données Adobe Experience Platform. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement pour ces variables.

## Définition de l’événement d’achat dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

L’événement d’achat est une chaîne définie dans le cadre de la variable d’événements.

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## Déduplication des événements d’achat

Lorsque vous déclenchez un événement d’achat, Adobe vérifie les éléments suivants :

* L’accès contient-il la variable `purchaseID` ? Dans le cas contraire, Adobe utilise les informations de l’accès pour créer un « identifiant d’achat temporaire ». Cet identifiant d’achat temporaire s’applique uniquement au visiteur de l’accès. Les cinq identifiants d’achat temporaires précédents sont stockés pour chaque identifiant visiteur par suite de rapports.
* L’identifiant d’achat temporaire correspond-il à l’un des cinq derniers identifiants d’achat temporaire stockés ? Si tel est le cas, la demande d’image est considérée comme un achat en double. Aucune variable de conversion, y compris l’événement d’achat, ne figure dans les rapports.
* Si la variable `purchaseID` est définie, correspond-elle à une valeur déjà collectée dans la suite de rapports pour tous les visiteurs ? Si tel est le cas, la demande d’image est considérée comme un achat en double. Aucune variable de conversion, y compris l’événement d’achat, ne figure dans les rapports.
