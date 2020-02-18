---
title: writeSecureCookies
description: Permet à AppMeasurement de définir des cookies avec l’attribut Secure.
translation-type: tm+mt
source-git-commit: 117a3c1ad411b25d8277b5678915b76eadd232a7

---


# writeSecureCookies

La `writeSecureCookies` variable permet à AppMeasurement de définir des cookies [](https://en.wikipedia.org/wiki/Secure_cookie) sécurisés pour Analytics. Ce paramètre s’applique aux cookies d’identification des visiteurs définis par AppMeasurement et aux cookies que vous définissez à l’aide de la `Util.CookieWrite` méthode. Il nécessite AppMeasurement 2.18.0 ou une version ultérieure.

> [!NOTE] Si vous activez la `writeSecureCookies` variable, assurez-vous que tout le contenu de votre site est diffusé en toute sécurité via HTTPS.

## Création de cookies sécurisés dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.writeSecureCookies dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.writeSecureCookies` variable est une valeur booléenne qui détermine si AppMeasurement définit l’attribut Secure lors de la création d’un cookie. Its default value is `false`. Définissez cette variable sur `true` si tout le contenu de votre site est sécurisé et que vous souhaitez que les cookies définis par AppMeasurement possèdent l’attribut Secure.

```js
s.writeSecureCookies = true;
```
