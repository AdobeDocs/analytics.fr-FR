---
title: Util.getQueryParam
description: Renvoie la valeur d’un paramètre de chaîne de .
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Util.getQueryParam

Les paramètres de chaîne  dans une URL de navigateur contiennent fréquemment des données importantes pour Analytics. Utilisez la `Util.getQueryParam()` méthode pour récupérer les données de la chaîne de  du.

## Obtention des données de paramètre de chaîne de  dans Adobe Experience Platform Launch

Vous pouvez obtenir des données de paramètre de chaîne de  en définissant des valeurs dans les éléments de données.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Data Elements] onglet, puis cliquez sur l’élément de données souhaité (ou créez un élément de données).
4. Définissez la [!UICONTROL Extension] liste déroulante sur [!UICONTROL Core]et la [!UICONTROL Data Element Type] sur [!UICONTROL Query String Parameter].
5. Entrez le paramètre de chaîne de  du dans le champ de texte.

La valeur du paramètre de chaîne de  est stockée dans l’élément de données. Vous pouvez ensuite référencer l’élément de données dans les règles pour affecter des variables Analytics.

## s.Util.getQueryParam() dans AppMeasurement et lancement de l’éditeur de code personnalisé

Appelez la `s.Util.getQueryParam()` méthode pour récupérer une valeur de chaîne de  à partir de l’URL du navigateur. L’argument de chaîne contenant un paramètre de chaîne de  est obligatoire. Cette méthode renvoie une chaîne que vous pouvez affecter aux variables Analytics :

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

Un deuxième argument facultatif vous permet de spécifier la chaîne à vérifier pour les paramètres de chaîne de . Par défaut, l’utilitaire examine l’URL du navigateur.

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

Un troisième argument facultatif vous permet de personnaliser le délimiteur de chaîne de  du. Its default value is `&`. Vous pouvez modifier cette valeur si votre chaîne de  utilise un délimiteur différent.

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

> [!TIP] Un module externe similaire nommé [`s.getQueryParam`](../plugins/getqueryparam.md) est disponible. Ce module externe contient des fonctionnalités plus avancées, mais il est également plus complexe et n’est pas inclus par défaut dans AppMeasurement.
