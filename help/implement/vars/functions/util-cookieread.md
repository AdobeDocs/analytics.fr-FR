---
title: Util.cookieRead
description: Obtient la valeur d’un cookie.
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Util.cookieRead

Les cookies peuvent stocker et récupérer des informations sur plusieurs pages du même domaine. Utilisez la `Util.cookieRead` méthode pour récupérer une valeur d’un cookie.

## Lire les cookies dans Adobe Experience Platform Launch

Vous pouvez lire les cookies en définissant des valeurs dans les éléments de données.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet Eléments [!UICONTROL de] données, puis cliquez sur l’élément de données souhaité (ou créez un élément de données).
4. Définissez la liste déroulante [!UICONTROL Extension] sur [!UICONTROL Core]et le Type [!UICONTROL d’élément de] données sur [!UICONTROL Cookie.]
5. Entrez le nom du cookie dans le champ de texte.

La valeur du cookie est stockée dans l’élément de données. Vous pouvez ensuite référencer l’élément de données dans les règles pour affecter des variables Analytics.

## s.Util.cookieRead() dans l’éditeur de code personnalisé AppMeasurement et de lancement

Appelez la `s.Util.cookieRead()` méthode pour lire une valeur de cookie. Son seul argument est une chaîne obligatoire. Cette méthode renvoie une chaîne contenant la valeur du cookie. Si les cookies n’existent pas, une chaîne vide est renvoyée.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
