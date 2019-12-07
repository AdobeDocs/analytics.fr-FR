---
description: Elle efface les valeurs suivantes de l’objet d’instance. Cette fonction supprime les éléments (en les définissant comme « undefined »).
keywords: Analytics Implementation
title: Fonction s.clearVars()
topic: Developer and implementation
uuid: 43c425bc-15ae-4892-a5a5-e1defcb25ff4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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

