---
title: eVar (variables de marchandisage)
description: Variables personnalisées associées à des produits individuels.
feature: Appmeasurement Implementation
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/BdChWcR9AJqLZ0KjOxSvFAjB8-58JmmGahrpvTyFeFI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 29%
---
# eVar (marchandisage)

>[!BEGINSHADEBOX]

*Cette page d’aide décrit comment implémenter des eVars de marchandisage. Pour plus d’informations sur le fonctionnement des eVars de marchandisage en tant que dimension, consultez [eVar (Dimension de marchandisage)](/help/components/dimensions/evar-merchandising.md) dans le guide d’utilisation Composants*.

>[!ENDSHADEBOX]

Les eVars de marchandisage lient une valeur à des produits individuels, de sorte que les événements de succès impliquant chaque produit soient crédités à la valeur liée à ce produit. Vous pouvez définir la valeur de l’une des deux façons suivantes :

* **[!UICONTROL Syntaxe du produit]** : définissez la valeur de chaque produit dans la variable [`products`](products.md).
* **[!UICONTROL Syntaxe de la variable de conversion]** : définissez la valeur dans l’eVar lui-même. La valeur se lie aux produits sur un accès contenant un événement de liaison.

Pour connaître le fonctionnement de la liaison, de l’attribution et de l’expiration, consultez [eVar (dimension de marchandisage)](/help/components/dimensions/evar-merchandising.md).

## Configurer des eVars dans les paramètres de la suite de rapports

Avant d’utiliser des eVars dans votre mise en œuvre, veillez à configurer l’eVar selon la syntaxe souhaitée dans les paramètres de la suite de rapports. Reportez-vous à la section [Variables de conversion](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) dans le guide Administrateur.

>[!WARNING]
>
>Une configuration incorrecte des eVars de marchandisage entraîne des valeurs inattendues ou une perte de données pour la variable. Veillez à ce qu’elles soient correctement configurées pour votre implémentation.

## Choisir une syntaxe

Utilisez [!UICONTROL &#x200B; Syntaxe du produit &#x200B;] lorsque la valeur de marchandisage est disponible au moment où vous définissez la variable de `products` ou lorsque les produits d’un même accès ont besoin de valeurs différentes. Utilisez [!UICONTROL &#x200B; Syntaxe de la variable de conversion &#x200B;] lorsque la valeur est connue avant le produit, par exemple le terme de recherche ou la campagne interne qui a amené le visiteur au produit. Pour une comparaison complète[&#128279;](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work) consultez la section  Fonctionnement de la liaison et de l’affectation .

## Mise en œuvre à l’aide de la syntaxe du produit

Lorsque la [!UICONTROL syntaxe du produit] est activée, la valeur de marchandisage est définie directement dans la variable `products`, de sorte que les événements de liaison ne sont pas utilisés. Les eVars de marchandisage se trouvent dans le dernier segment de chaque produit :

```js
s.products = "[category];[name];[quantity];[revenue];[events];[eVars]";
```

Délimitez plusieurs eVars de marchandisage sur le même produit avec une barre verticale (`|`). Les espaces réservés vides pour la quantité, le chiffre d’affaires et les événements sont requis même si vous ne les utilisez pas. Sans eux, la valeur eVar est ignorée.

La valeur est liée au produit sur cet accès. Le remplacement d’une liaison existante par une valeur ultérieure dépend du paramètre [!UICONTROL Allocation]. Voir [Fonctionnement de la liaison et de l’affectation](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work).

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

### Syntaxe de produit utilisant le SDK Web

Si vous utilisez l’objet [**XDM**](/help/implement/aep-edge/xdm-var-mapping.md), les variables de marchandisage de syntaxe de produit utilisent les champs XDM suivants :

* Les eVars de marchandisage de syntaxe de produit sont mappées sous `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar1` à `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar250`.
* Les événements de marchandisage de syntaxe de produit sont mappés sous `xdm.productListItems[]._experience.analytics.event1to100.event1.value` à `xdm.productListItems[]._experience.analytics.event901to1000.event1000.value`. Les champs XDM de [sérialisation d’événements](events/event-serialization.md) sont mappés sous `xdm.productListItems[]._experience.analytics.event1to100.event1.id` à `xdm.productListItems[]._experience.analytics.event901to1000.event1000.id`.

>[!NOTE]
>
>Lorsque vous définissez des événements sous `productListItems`, vous n’avez pas besoin de les définir dans la chaîne d’événement. S’ils sont définis aux deux endroits, la valeur de la chaîne d’événement est prioritaire.

L’exemple suivant illustre un seul [produit](products.md) utilisant plusieurs eVars et événements de marchandisage :

```json
"productListItems": [
  {
    "name": "Bahama Shirt",
    "priceTotal": "12.99",
    "quantity": 3,
    "_experience": {
      "analytics": {
        "customDimensions" : {
          "eVars" : {
            "eVar10" : "green",
            "eVar33" : "large"
          }
        },
        "event1to100" : {
          "event4" : {
            "value" : 1
          },
          "event10" : {
            "value" : 2,
            "id" : "abcd"
          }
        }
      }
    }
  }
]
```

L’exemple d’objet ci-dessus serait envoyé à Adobe Analytics en tant que `";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"`.

Si vous utilisez l’[**objet de données**](/help/implement/aep-edge/data-var-mapping.md), les eVars de marchandisage de syntaxe de produit sont définies dans `data.__adobe.analytics.products`, en utilisant la même syntaxe que la variable de `products` AppMeasurement. Équivalent de l’objet de données de l’exemple XDM ci-dessus :

```json
"data": {
  "__adobe": {
    "analytics": {
      "products": ";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"
    }
  }
}
```

## Mise en œuvre à l’aide de la syntaxe de variable de conversion

Utilisez [!UICONTROL &#x200B; Syntaxe de la variable de conversion &#x200B;] lorsque la valeur eVar n’est pas disponible pour être définie dans la variable `products`. Ce scénario signifie généralement que votre page de produit ne comporte aucun contexte du canal de marchandisage ou de la méthode de recherche. Dans ce cas, définissez l’eVar de marchandisage sur ou avant la page sur laquelle l’événement de liaison se produit. La valeur persiste jusqu’à son expiration ou jusqu’à ce qu’elle soit remplacée par une nouvelle valeur.

Lorsqu’un accès contient à la fois la variable `products` et un [!UICONTROL événement de liaison de marchandisage] sélectionné, la valeur actuelle d’eVar se lie à chaque produit de cet accès. Définir eVar avec un produit sans événement de liaison ne lie pas la valeur. Le remplacement d’une liaison existante par une liaison ultérieure dépend du paramètre [!UICONTROL Allocation]. Voir [Fonctionnement de la liaison et de l’affectation](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work).

Pour obtenir un exemple qui définit plusieurs eVars de méthode de recherche de produit à la fois, consultez [Bonne pratique : méthodes de recherche de produit](/help/components/dimensions/evar-merchandising.md#best-practice-product-finding-methods).

L’exemple suivant définit une eVar de marchandisage avant l’événement de liaison :

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

Si [!UICONTROL Événement d’affichage du produit] est un événement de liaison, la valeur `"Aviary"` pour `eVar1` est liée au `"Canary"` du produit. Les événements de succès suivants impliquant ce produit sont crédités à `"Aviary"`. La valeur `"Aviary"` se lie également aux produits lors des accès ultérieurs qui contiennent un événement de liaison, jusqu’à ce que l’une des conditions suivantes soit remplie :

* L’eVar arrive à expiration (en fonction du paramètre [!UICONTROL Expire après]).
* L’eVar de marchandisage est remplacée par une nouvelle valeur.

### Syntaxe des variables de conversion utilisant le SDK Web

Si vous utilisez l’objet [**XDM**](/help/implement/aep-edge/xdm-var-mapping.md), la syntaxe fonctionne de la même manière que l’implémentation d’autres [eVars](evar.md) et [events](events/events-overview.md). Si vous utilisez l’[**objet de données**](/help/implement/aep-edge/data-var-mapping.md), la syntaxe suit AppMeasurement.

La mise en miroir XDM de l’exemple AppMeasurement ci-dessus se présenterait comme suit.

Définissez l’eVar sur le même appel d’événement ou l’appel d’événement précédent :

```json
"_experience": {
  "analytics": {
    "customDimensions": {
      "eVars": {
        "eVar1" : "Aviary"
      }
    }
  }
}
```

Définissez l’événement de liaison et les valeurs de la chaîne des produits :

```json
"commerce": {
  "productViews" : {
    "value" : 1
  }
},
"productListItems": [
  {
    "name": "Canary"
  }
]
```

Les objets de données reflétant l’exemple d’AppMeasurement ci-dessus ressembleraient à ce qui suit.

Définissez l’eVar sur le même appel d’événement ou l’appel d’événement précédent :

```json
"data": {
  "__adobe": {
    "analytics": {
      "eVar1": "Aviary"
    }
  }
}
```

Définissez l’événement de liaison et les valeurs de la chaîne des produits :

```json
"data": {
  "__adobe": {
    "analytics": {
      "events": "prodView",
      "products": ";Canary"
    }
  }
}
```

