---
description: Elle efface les valeurs suivantes de l’objet d’instance. Cette fonction supprime les éléments (en les définissant comme « undefined »).
keywords: Analytics Implementation
solution: Analytics
title: Fonction s.clearVars()
topic: Developer and implementation
uuid: 43c425bc-15ae-4892-a5a5-e1defcb25ff4
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Fonction s.clearVars()

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
>`clearVars()`la variable est incluse dans [AppMeasurement pour JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md), mais elle n’est pas disponible en code H ou version antérieure.

