---
title: Util.cookieWrite
description: Permet d’inscrire une valeur dans un cookie.
feature: Variables
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 70%

---

# Util.cookieWrite

Les cookies peuvent stocker et récupérer des informations sur plusieurs pages du même domaine. Utilisez la méthode `Util.cookieWrite()` pour définir une valeur sur un cookie. Vous pouvez utiliser la méthode [`Util.cookieRead()`](util-cookieread.md) pour récupérer les valeurs définies à l’aide de `Util.cookieWrite()`.

## Définir des cookies à l’aide de l’extension Adobe Analytics et de l’extension SDK Web

La collecte de données Adobe Experience Platform ne permet pas de définir des cookies dans l’interface.

## s.Util.cookieWrite() dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Appelez la méthode `s.Util.cookieWrite()` pour définir un cookie sur la valeur souhaitée.

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

Un troisième argument facultatif est disponible, qui détermine le moment où le cookie expire. Les cookies définis à l’aide de `s.Util.cookieWrite()` expirent à la fin de la session du navigateur par défaut.

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## Exemples

Vous pouvez instancier une variable en cas de réussite de l’écriture d’un cookie. Cette variable est une valeur booléenne.

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```
