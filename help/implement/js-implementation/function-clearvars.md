---
description: Elle efface les valeurs suivantes de l’objet d’instance. Cette fonction supprime les éléments (en les définissant comme « undefined »).
keywords: Mise en œuvre d’Analytics
seo-description: Elle efface les valeurs suivantes de l’objet d’instance. Cette fonction supprime les éléments (en les définissant comme « undefined »).
seo-title: La fonction s.clearVars()
solution: Analytics
title: La fonction s.clearVars()
topic: Développeur et mise en œuvre
uuid: 43 c 425 bc -15 ae -4892-a 5 a 5-e 1 defcb 25 ff 4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# La fonction s.clearVars()

Elle efface les valeurs suivantes de l’objet d’instance. Cette fonction supprime les éléments (en les définissant comme « undefined »).

* `props`
* `eVars`
* `hier`
* `list`
* `events`
* `eventList`
* `products`
* `productsList`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

Par exemple :

```js
s.clearVars()
```

>[!NOTE]
>
>`clearVars()` est incluse dans [appmeasurement pour JavaScript](../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) mais n'est pas disponible dans le code H et les versions précédentes.

