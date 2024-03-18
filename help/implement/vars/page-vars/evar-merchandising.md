---
title: eVar (variables de marchandisage)
description: Variables personnalisées liées à des produits individuels.
feature: Variables
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 90%

---

# eVar (marchandisage)

*Cette page d’aide décrit comment implémenter des eVars de marchandisage. Pour plus d’informations sur le fonctionnement des eVars de marchandisage en tant que dimension, consultez [eVars (dimensions de marchandisage)](/help/components/dimensions/evar-merchandising.md) dans le guide d’utilisation Composants.*

Pour obtenir des informations détaillées sur le fonctionnement des eVars de marchandisage, consultez la page [eVars de marchandisage et méthodes de recherche de produit](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=fr).

## Configurer des eVars dans les paramètres de la suite de rapports

Avant d’utiliser des eVars dans votre mise en œuvre, veillez à configurer l’eVar selon la syntaxe souhaitée dans les paramètres de la suite de rapports. Reportez-vous à la section [Variables de conversion](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) dans le guide Administrateur.

>[!WARNING]
>
>Si les eVars de marchandisage ne sont pas correctement configurées, cela entraîne des valeurs inattendues ou une perte de données pour la variable. Veillez à ce qu’elles soient correctement configurées pour votre implémentation.

## Implémentation à l’aide de la syntaxe du produit

Lorsque le paramètre « Syntaxe du produit » est activé, la catégorie de marchandisage est directement remplie dans la variable `products`. La sélection et la définition d’un événement de liaison ne sont donc pas requises. Il est vivement conseillé d’utiliser cette méthode, à moins que la valeur ne soit pas disponible pour être définie dans la variable `products` lorsque l’événement de succès se produit.

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

La valeur pour `eVar1` est affectée au produit. Tous les événements de succès suivants qui impliquent ce produit sont crédités à la valeur eVar.

### Syntaxe de produit utilisant le SDK Web

Si vous utilisez la variable [**Objet XDM**](/help/implement/aep-edge/xdm-var-mapping.md), les variables de marchandisage de syntaxe de produit utilisent les champs XDM suivants :

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

Si vous utilisez la variable [**objet de données**](/help/implement/aep-edge/data-var-mapping.md), utilisation du marchandisage en eVar `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` selon la syntaxe de l’AppMeasurement.

## Implémentation à l’aide de la syntaxe de la variable de conversion

La syntaxe de la variable de conversion est utilisée lorsque la valeur eVar n’est pas disponible pour être définie dans la variable `products`. Ce scénario signifie généralement que votre page n’est pas en mesure de déterminer le canal de marchandisage ou la méthode de recherche. Dans ce cas, vous devez définir la variable de marchandisage avant d’arriver à la page du produit et la valeur persiste jusqu’à l’événement de liaison.

Lorsque l’événement de liaison sélectionné en cours de configuration se produit, la valeur persistante de l’eVar est associée au produit. Par exemple, si `prodView` est spécifié en tant qu’événement de liaison, la catégorie de marchandisage n’est liée à la liste des produits en cours qu’au moment où l’événement se produit. Seuls les événements de liaison ultérieurs pourront mettre à jour une eVar de marchandisage qui a déjà été affectée à un produit.

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

La valeur `"Aviary"` pour `eVar1` est affectée au produit `"Canary"`. Tous les événements de succès ultérieurs qui impliquent ce produit sont crédités à `"Canary"`. De plus, la valeur actuelle de la variable de marchandisage sera liée à tous les produits ultérieurs, jusqu’à ce que l’une des conditions suivantes soit remplie :

* L’expiration de l’eVar (sur la base du paramètre « Expire After »)
* L’eVar de marchandisage est remplacée par une nouvelle valeur.

### Syntaxe des variables de conversion utilisant le SDK Web

Si vous utilisez la variable [**Objet XDM**](/help/implement/aep-edge/xdm-var-mapping.md), la syntaxe fonctionne de la même manière que pour l’implémentation d’autres [eVars](evar.md) et [events](events/events-overview.md). La mise en miroir XDM de l’exemple ci-dessus ressemblerait à ce qui suit :

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

Si vous utilisez la variable [**objet de données**](/help/implement/aep-edge/data-var-mapping.md), les objets de données correspondant à l’exemple ci-dessus se présentent comme suit :

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
