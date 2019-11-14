---
description: Obtient la valeur d’un cookie.
keywords: Analytics Implementation
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: Developer and implementation
uuid: 825a75c6-b804-4bfe-b23a-907113b8bfa6
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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

