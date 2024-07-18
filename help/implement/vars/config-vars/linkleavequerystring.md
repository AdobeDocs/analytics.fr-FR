---
title: linkLeaveQueryString
description: Permet de conserver les chaînes de requête dans les dimensions de suivi des liens.
feature: Variables
exl-id: 266f7d9c-803d-4dbe-95a1-282230012878
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 84%

---

# linkLeaveQueryString

AppMeasurement supprime par défaut les chaînes de requête des URL de suivi des liens. Utilisez la variable `linkLeaveQueryString` pour conserver les chaînes de requête dans les dimensions de suivi des liens.

Pour certains rapports Liens de sortie et Téléchargements de fichiers, la partie importante de l’URL peut se trouver dans la chaîne de requête. Par exemple, un lien de téléchargement tel que `https://example.com/download.asp?filename=myfile.exe` contient des informations de lien importantes dans la chaîne de requête.

Si les informations de suivi des liens ne figurent pas dans les URL de votre site, l’utilisation de cette variable n’est pas nécessaire. L’extraction de chaînes de requête à partir des URL de suivi des liens permet de limiter le nombre de valeurs uniques contenues dans la dimension.

L’activation de `linkLeaveQueryString` s’applique à toutes les dimensions de suivi des liens (y compris les liens personnalisés, les liens de sortie et les liens de téléchargement).

>[!TIP]
>
>Cette variable n’affecte pas les dimensions en dehors du suivi des liens. Elle affecte uniquement les liens personnalisés, les liens de sortie et les liens de téléchargement.

## Gestion des chaînes de requête de lien à l’aide du SDK Web

Les chaînes de requête ne sont pas retirées du champ XDM `web.webInteraction.URL`. Si vous souhaitez supprimer les chaînes de requête de ce champ XDM, vous pouvez le modifier à l’aide de `onBeforeEventSend`.

## Conserver les paramètres d’URL à l’aide de l’extension Adobe Analytics

[!UICONTROL Conserver les paramètres d’URL] est une case à cocher située sous l’accordéon [!UICONTROL Suivi des liens] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Suivi des liens], qui affiche la case à cocher [!UICONTROL Conserver les paramètres d’URL].

Cochez cette case si vous souhaitez inclure des chaînes de requête dans les dimensions de suivi des liens.

## s.linkLeaveQueryString dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.linkLeaveQueryString` est une valeur booléenne. Sa valeur par défaut est `false`.

* Si cette variable est définie sur `true`, les chaînes de requête sont conservées dans les URL de suivi des liens.
* Si cette variable est définie sur `false` ou non définie, les chaînes de requête sont retirées des URL de suivi des liens.

```js
s.linkLeaveQueryString = true;
```

## Exemple

Soyez prudent lorsque vous définissez cette variable sur true, car elle peut avoir un impact sur les filtres de suivi des liens tels que [`linkInternalFilters`](linkinternalfilters.md), [`linkExternalFilters`](linkexternalfilters.md) et [`linkDownloadFiletypes`](linkdownloadfiletypes.md).

Examinez l’exemple suivant comme s’il se trouvait sur `adobe.com` :

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
