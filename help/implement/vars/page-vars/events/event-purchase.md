---
title: Événement d’achat
description: Utilisez l’événement d’achat pour collecter des données pour les mesures Commandes, Unités et Recettes.
feature: Appmeasurement Implementation
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
role: Admin, Developer
TQID: https://experienceleague.adobe.com/r-L330P6HA5qWBmEW-2LwECo-d3dhVK1ovWsfraErXE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 75%

---

# Événement d’achat

L’événement d’achat est une valeur de la variable `events`. Cette valeur est utile pour les entreprises qui souhaitent collecter des données sur les recettes générées par leur site. Elle dépend fortement des variables [`products`](../products.md) et [`purchaseID`](../purchaseid.md).

Lorsque vous définissez un événement d’achat, celui-ci affecte les mesures suivantes :

* La mesure Commandes est incrémentée de 1
* La mesure Unités est incrémentée en fonction du nombre de produits dans la variable `products`
* La mesure Recettes augmente de la somme des paramètres de prix dans la variable `products`

>[!NOTE]
>
>Le chiffre d’affaires n’est pas multiplié par le champ de quantité. Par exemple, `s.products="Womens;Socks;5;4.50"` ne transfère pas 22,50 $ dans les revenus; il transfère 4,50 $. Assurez-vous que votre implémentation transmet le chiffre d’affaires total pour la quantité répertoriée. Par exemple : `s.products="Womens;Socks;5;22.50"`.

## Définir l’événement d’achat à l’aide de Web SDK

Si vous utilisez l’objet [**XDM**](/help/implement/aep-edge/xdm-var-mapping.md), l’événement d’achat utilise les champs XDM suivants :

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

Si vous utilisez l’objet [**data**](/help/implement/aep-edge/data-var-mapping.md), l’événement d’achat utilise `data.__adobe.analytics.events`, en suivant la syntaxe de chaîne AppMeasurement.

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
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Events] et définissez la liste déroulante [!UICONTROL Events] sur [!UICONTROL purchase].

D’autres variables dépendantes telles que `products` et `purchaseID` ne comportent pas de champs dédiés dans l’extension Analytics de la collecte de données Adobe Experience Platform. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement pour ces variables.

## Définissez l’événement d’achat dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

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
