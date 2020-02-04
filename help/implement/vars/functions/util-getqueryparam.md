---
title: Util.getQueryParam
description: Renvoie la valeur d’un paramètre de chaîne de requête.
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Util.getQueryParam

Les paramètres de chaîne de requête dans une URL de navigateur contiennent fréquemment des données importantes pour Analytics. Utilisez la `Util.getQueryParam` méthode pour récupérer les données de la chaîne de requête.

## Obtention des données de paramètre de chaîne de requête dans Adobe Experience Platform Launch

Vous pouvez obtenir des données de paramètre de chaîne de requête en définissant des valeurs dans les éléments de données.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet Eléments [!UICONTROL de] données, puis cliquez sur l’élément de données souhaité (ou créez un élément de données).
4. Définissez la liste déroulante [!UICONTROL Extension] sur [!UICONTROL Core]et le Type [!UICONTROL d’élément de] données sur Paramètre de chaîne de [!UICONTROL requête.]
5. Entrez le paramètre de chaîne de requête dans le champ de texte.

La valeur du paramètre de chaîne de requête est stockée dans l’élément de données. Vous pouvez ensuite référencer l’élément de données dans les règles pour affecter des variables Analytics.

## s.Util.getQueryParam() dans AppMeasurement et lancement de l’éditeur de code personnalisé

Appelez la `s.Util.getQueryParam()` méthode pour récupérer une valeur de chaîne de requête à partir de l’URL du navigateur. L&#39;argument de chaîne contenant un paramètre de chaîne de requête est obligatoire. Cette méthode renvoie une chaîne que vous pouvez affecter aux variables Analytics :

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

Un troisième argument facultatif vous permet de personnaliser le délimiteur de chaîne de requête. Its default value is `&`. Vous pouvez modifier cette valeur si votre chaîne de requête utilise un délimiteur différent.

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

> [!NOTE] Les versions précédentes d’AppMeasurement comportaient un module externe nommé `s.getQueryParam` disponible. Ce module externe n’est plus nécessaire, car il est désormais inclus dans AppMeasurement par défaut.
