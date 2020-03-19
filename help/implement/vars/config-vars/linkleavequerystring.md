---
title: linkLeaveQueryString
description: Permet de conserver les chaînes de  dans les dimensions de suivi des liens.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkLeaveQueryString

AppMeasurement supprime par défaut  chaînes de des URL de suivi de liens. Utilisez la `linkLeaveQueryString` variable pour conserver  chaînes dans les dimensions de suivi des liens.

Pour certains liens de sortie et de téléchargement, la partie importante de l’URL peut se trouver dans la chaîne de  du. Par exemple, un lien de téléchargement tel que `https://example.com/download.asp?filename=myfile.exe` contient des informations importantes sur le lien dans la chaîne de  du.

Si les informations de suivi des liens ne figurent pas dans les URL de votre site, l’utilisation de cette variable n’est pas nécessaire. L’extraction de chaînes de à partir des URL de suivi des liens permet de limiter le nombre de valeurs uniques contenues dans la dimension.

L’activation `linkLeaveQueryString` s’applique à toutes les dimensions de suivi des liens (y compris les liens personnalisés, les liens de sortie et les liens de téléchargement).

> [!TIP] Cette variable n’affecte pas les dimensions en dehors du suivi des liens. Elle affecte uniquement les liens personnalisés, les liens de sortie et les liens de téléchargement.

## Conserver les paramètres d’URL dans Adobe Experience Platform Launch

[!UICONTROL Keep URL Parameters] est une case à cocher sous l’ [!UICONTROL Link Tracking] accordéon lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Configure] bouton sous Adobe Analytics.
4. Développez l’ [!UICONTROL Link Tracking] accordéon, qui affiche la [!UICONTROL Keep URL Parameters] case à cocher.

Cochez cette case si vous souhaitez inclure  chaînes de dans les dimensions de suivi des liens.

## s.linkLeaveQueryString dans l&#39;éditeur de code personnalisé AppMeasurement et Launch

La `s.linkLeaveQueryString` variable est une valeur booléenne. Its default value is `false`.

* Si cette variable est définie sur `true`, les chaînes  sont conservées dans les URL de suivi des liens.
* Si cette variable est définie sur `false` ou non, les chaînes de  sont retirées des URL de suivi des liens.

```js
s.linkLeaveQueryString = true;
```

## Exemple

Soyez attentif lorsque vous définissez cette variable sur true, car elle peut avoir un impact sur le de suivi des liens,  par exemple [`linkInternalFilters`](linkinternalfilters.md), [`linkExternalFilters`](linkexternalfilters.md)et [`linkDownloadFiletypes`](linkdownloadfiletypes.md).

Examinez l’exemple suivant comme s’il était activé `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
