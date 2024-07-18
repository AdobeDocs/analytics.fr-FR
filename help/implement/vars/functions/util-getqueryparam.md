---
title: Util.getQueryParam
description: Renvoie la valeur d’un paramètre de chaîne de requête.
feature: Variables
exl-id: d29d6cd9-f85f-475b-a7a8-73785aa4ae7b
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 79%

---

# Util.getQueryParam

Les paramètres de chaîne de requête dans une URL de navigateur contiennent fréquemment des données importantes pour Analytics. Utilisez la méthode `Util.getQueryParam()` pour récupérer les données de la chaîne de requête.

## Obtention des données de paramètre de chaîne de requête à l’aide de l’extension Adobe Analytics et de l’extension SDK web

Vous pouvez obtenir des données de paramètre de chaîne de requête en définissant des valeurs dans les éléments de données.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Éléments de données], puis cliquez sur l’élément de données souhaité (ou créez un élément de données).
4. Définissez la liste déroulante [!UICONTROL Extension] sur **[!UICONTROL Core]** et le [!UICONTROL Type d’élément de données] sur **[!UICONTROL Paramètre de chaîne de requête]**.
5. Entrez le paramètre de chaîne de requête dans le champ de texte.

La valeur du paramètre de chaîne de requête est stockée dans l’élément de données. Vous pouvez ensuite référencer l’élément de données dans les règles pour affecter les variables souhaitées.

## s.Util.getQueryParam() dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

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

>[!TIP]
>
>Un plug-in similaire nommé [`s.getQueryParam`](../plugins/getqueryparam.md) est disponible. Ce plug-in contient des fonctionnalités plus avancées, mais il est également plus complexe et n’est pas inclus par défaut dans AppMeasurement.
