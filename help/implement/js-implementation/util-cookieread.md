---
description: Obtient la valeur d’un cookie.
keywords: Analytics Implementation
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: Developer and implementation
uuid: 825a75c6-b804-4bfe-b23a-907113b8bfa6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Util.cookieRead

Obtient la valeur d’un cookie.

**Syntaxe :**

```
s.Util.cookieRead(key)
```

**Paramètres:**

| Paramètre | Description |
|---|---|
| key | (obligatoire) clé pour laquelle écrire une valeur dans les cookies. |

**Retours:**

Valeur du cookie ou chaîne vide si le cookie est introuvable.

**Exemple :**

```js
var myCookie = s.Util.cookieRead("my_cookie");
```

