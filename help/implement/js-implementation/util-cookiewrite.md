---
description: Ecrit une valeur dans un cookie.
keywords: Mise en œuvre d’Analytics
seo-description: Ecrit une valeur dans un cookie.
seo-title: Util.cookieWrite
solution: Analytics
subtopic: AppMeasurement pour JavaScript
title: Util.cookieWrite
topic: Développeur et mise en œuvre
uuid: 8d526e4c-6d7a-4119-9434-d7ce4fbb7577
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Util.cookieWrite

Ecrit une valeur dans un cookie.

**Syntaxe :**

```
s.Util.cookieWrite(key, value [,expire])
```

**Paramètres :**

| Paramètre | Description |
|---|---|
| key | (obligatoire) clé pour laquelle écrire une valeur dans les cookies. |
| value | (facultatif) valeur à écrire dans les cookies. |
| expire | (facultatif) objet de date contenant la date d’expiration du cookie. Le paramètre par défaut est l’utilisation d’un cookie de session. |

**Retours :**

**Exemple :**

```js
//set a cookie with an expiration 6 months from now 
var date = new Date(); 
date.setMonth(date.getMonth() + 6); 
var success = s.Util.cookieWrite("my_cookie", "my_value", date);
```

