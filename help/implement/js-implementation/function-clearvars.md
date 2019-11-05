---
description: Elle efface les valeurs suivantes de l’objet d’instance. Cette fonction supprime les éléments (en les définissant comme « undefined »).
keywords: Mise en œuvre d’Analytics
seo-description: Elle efface les valeurs suivantes de l’objet d’instance. Cette fonction supprime les éléments (en les définissant comme « undefined »).
seo-title: Fonction s.clearVars()
solution: Analytics
title: Fonction s.clearVars()
topic: Développeur et mise en œuvre
uuid: 43c425bc-15ae-4892-a5a5-e1defcb25ff4
translation-type: tm+mt
source-git-commit: 2fc1a01aced4cf2b165b46353418fbee9b83bee5

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

