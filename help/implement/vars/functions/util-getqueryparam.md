---
title: Util.getQueryParam
description: Renvoie la valeur d’un paramètre de chaîne de requête.
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Util.getQueryParam

Les paramètres de chaîne de requête dans une URL de navigateur contiennent fréquemment des données importantes pour Analytics. Utilisez la méthode `Util.getQueryParam()` pour récupérer les données de la chaîne de requête.

## Obtention des données de paramètre de chaîne de requête dans Adobe Experience Platform Launch

Vous pouvez obtenir des données de paramètre de chaîne de requête en définissant des valeurs dans les éléments de données.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Éléments de données], puis cliquez sur l’élément de données souhaité (ou créez un élément de données).
4. Définissez la liste déroulante [!UICONTROL Extension] sur [!UICONTROL Core] et le [!UICONTROL Type d’élément de données] sur [!UICONTROL Paramètre de chaîne de requête].
5. Entrez le paramètre de chaîne de requête dans le champ de texte.

La valeur du paramètre de chaîne de requête est stockée dans l’élément de données. Vous pouvez ensuite référencer l’élément de données dans les règles pour affecter des variables Analytics.

## s.Util.getQueryParam() dans AppMeasurement et l’éditeur de code personnalisé de Launch

Appelez la méthode `s.Util.getQueryParam()` pour récupérer une valeur de chaîne de requête à partir de l’URL du navigateur. L’argument de chaîne contenant un paramètre de chaîne de requête est obligatoire. Cette méthode renvoie une chaîne que vous pouvez affecter aux variables Analytics :

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

Un deuxième argument facultatif vous permet de spécifier la chaîne à vérifier pour les paramètres de chaîne de requête. Par défaut, l’utilitaire examine l’URL du navigateur.

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

Un troisième argument facultatif vous permet de personnaliser le délimiteur de chaîne de requête. Sa valeur par défaut est `&`. Vous pouvez modifier cette valeur si votre chaîne de requête utilise un délimiteur différent.

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

>[!TIP] Un plug-in similaire nommé [`s.getQueryParam`](../plugins/getqueryparam.md) est disponible. Ce plug-in contient des fonctionnalités plus avancées, mais il est également plus complexe et n’est pas inclus par défaut dans AppMeasurement.
