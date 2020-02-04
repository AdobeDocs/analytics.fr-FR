---
title: Util.cookieWrite
description: Ecrit une valeur pour un cookie.
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Util.cookieWrite

Les cookies peuvent stocker et récupérer des informations sur plusieurs pages du même domaine. Utilisez la `Util.cookieWrite` méthode pour définir une valeur sur un cookie. Vous pouvez utiliser la `Util.cookieRead` méthode pour récupérer les valeurs définies à l’aide `Util.cookieWrite`.

## Définition de cookies dans Adobe Experience Platform Launch

Launch ne permet pas de définir des cookies dans l’interface. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.Util.cookieWrite() dans l’éditeur de code personnalisé AppMeasurement et de lancement

Appelez la `s.Util.cookieWrite()` méthode pour définir un cookie sur la valeur souhaitée.

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
