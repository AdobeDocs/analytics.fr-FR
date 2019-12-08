---
description: Ecrit une valeur dans un cookie.
keywords: Analytics Implementation
subtopic: JavaScript AppMeasurement
title: Util.cookieWrite
topic: Developer and implementation
uuid: 8d526e4c-6d7a-4119-9434-d7ce4fbb7577
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Util.cookieWrite

Ecrit une valeur dans un cookie.

**Syntaxe :**

```
s.Util.cookieWrite(key, value [,expire])
```

**Paramètres:**

| Paramètre | Description |
|---|---|
| key | (obligatoire) clé pour laquelle écrire une valeur dans les cookies. |
| value | (facultatif) valeur à écrire dans les cookies. |
| expire | (facultatif) objet de date contenant la date d’expiration du cookie. Le paramètre par défaut est l’utilisation d’un cookie de session. |

**Retours:**

**Exemple :**

```js
//set a cookie with an expiration 6 months from now 
var date = new Date(); 
date.setMonth(date.getMonth() + 6); 
var success = s.Util.cookieWrite("my_cookie", "my_value", date);
```

