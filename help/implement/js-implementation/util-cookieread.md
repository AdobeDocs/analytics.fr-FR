---
description: Obtient la valeur d’un cookie.
keywords: Mise en œuvre d’Analytics
seo-description: Obtient la valeur d'un cookie.
seo-title: Util.cookieRead
solution: Analytics
subtopic: AppMeasurement pour JavaScript
title: Util.cookieRead
topic: Développeur et mise en œuvre
uuid: 825 a 75 c 6-b 804-4 bfe-b 23 a -907113 b 8 bfa 6
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Util.cookieRead

Obtient la valeur d’un cookie.

**Syntaxe :**

```
s.Util.cookieRead(key)
```

**Paramètres :**

| Paramètre | Description |
|---|---|
| key | (obligatoire) clé pour laquelle écrire une valeur dans les cookies. |

**Retours :**

Valeur du cookie ou chaîne vide si le cookie est introuvable.

**Exemple :**

```js
var myCookie = s.Util.cookieRead("my_cookie");
```

