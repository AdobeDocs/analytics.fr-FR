---
title: writeSecureCookies
description: Permet à AppMeasurement de définir des cookies avec l’attribut Secure.
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# writeSecureCookies

La variable`writeSecureCookies` permet à AppMeasurement de définir des [cookies sécurisés](https://en.wikipedia.org/wiki/Secure_cookie) pour Analytics. Ce paramètre s’applique à la fois aux cookies identifiant visiteur définis par AppMeasurement et aux cookies que vous définissez à l’aide de la méthode `Util.CookieWrite()`. Elle nécessite AppMeasurement 2.18.0 ou une version ultérieure.

>[!IMPORTANT] Si vous activez la variable`writeSecureCookies`, assurez-vous que tout le contenu de votre site est diffusé en toute sécurité via HTTPS. AppMeasurement ne fonctionne pas si cette variable est activée et que votre page contient du contenu non sécurisé.

## Écrire des cookies sécurisés dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Launch pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.writeSecureCookies dans AppMeasurement et l’éditeur de code personnalisé Launch

La variable `s.writeSecureCookies` est une valeur booléenne qui détermine si AppMeasurement définit l’attribut Secure lors de la création d’un cookie. Sa valeur par défaut est `false`. Définissez cette variable sur `true` si tout le contenu de votre site est sécurisé et que vous souhaitez que les cookies définis par AppMeasurement possèdent l’attribut Secure.

```js
s.writeSecureCookies = true;
```
