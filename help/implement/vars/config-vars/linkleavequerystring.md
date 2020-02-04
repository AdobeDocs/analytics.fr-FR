---
title: linkLeaveQueryString
description: Permet de conserver les chaînes de requête dans les dimensions de suivi des liens.
translation-type: tm+mt
source-git-commit: e500332fe16887fa004858b07b59644837e183aa

---


# linkLeaveQueryString

AppMeasurement supprime par défaut les chaînes de requête des URL de suivi des liens. Utilisez la variable linkLeaveQueryString pour conserver les chaînes de requête dans les dimensions de suivi des liens.

Pour certains liens de sortie et de téléchargement, la partie importante de l’URL peut se trouver dans la chaîne de requête. Par exemple, un lien de téléchargement tel que `https://example.com/download.asp?filename=myfile.exe` contient des informations de lien importantes dans la chaîne de requête.

Si les informations de suivi des liens ne figurent pas dans les URL de votre site, l’utilisation de cette variable n’est pas nécessaire. L’extraction de chaînes de requête à partir des URL de suivi des liens permet de limiter le nombre de valeurs uniques contenues dans la dimension.

L’activation `linkLeaveQueryString` s’applique à toutes les dimensions de suivi des liens (y compris les liens personnalisés, les liens de sortie et les liens de téléchargement).

> [!TIP] Cette variable n’affecte pas les dimensions en dehors du suivi des liens. Elle affecte uniquement les liens personnalisés, les liens de sortie et les liens de téléchargement.

## Conserver les paramètres d’URL dans Adobe Experience Platform Launch

[!UICONTROL Conserver les paramètres] d’URL est une case à cocher située sous l’accordéon Suivi [!UICONTROL des] liens lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon Suivi des [!UICONTROL liens] , qui affiche la case à cocher [!UICONTROL Conserver les paramètres] d’URL.

Cochez cette case si vous souhaitez inclure des chaînes de requête dans les dimensions de suivi des liens.

## s.linkLeaveQueryString dans l&#39;éditeur de code personnalisé AppMeasurement et Launch

La `s.linkLeaveQueryString` variable est une valeur booléenne. Its default value is `false`.

* Si cette variable est définie sur `true`, les chaînes de requête sont conservées dans les URL de suivi des liens.
* Si cette variable est définie sur `false` ou non, les chaînes de requête sont retirées des URL de suivi des liens.

```js
s.linkLeaveQueryString = true;
```

## Exemple

Soyez prudent lorsque vous définissez cette variable sur true, car elle peut avoir un impact sur les filtres de suivi des liens tels `linkInternalFilters`, `linkExternalFilters`et `linkDownloadFiletypes`.

Examinez l’exemple suivant comme s’il était activé `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
