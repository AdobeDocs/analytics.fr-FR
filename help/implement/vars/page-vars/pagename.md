---
title: pageName
description: Nom de la page de votre site.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# pageName

La `pageName` variable stocke généralement le nom d’une page donnée. Il est utile de déterminer les pages les plus populaires. Cette variable renseigne la dimension &quot;Nom de page&quot;.

> [!NOTE] Cette dimension est toujours supprimée des appels de suivi de liens. Si vous souhaitez voir le nom de la page sur laquelle un lien a été suivi, pensez à copier cette variable dans une eVar.

Si cette variable n’est pas définie sur un appel de suivi de page donné, la [`pageURL`](pageurl.md) variable est utilisée à la place.

## Nom de page dans Adobe Experience Platform Launch

Vous pouvez définir le nom de la page lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Rules] onglet, puis cliquez sur la règle souhaitée (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une [!UICONTROL Adobe Analytics - Set Variables] action existante ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la [!UICONTROL Extension] liste déroulante sur Adobe Analytics et la [!UICONTROL Action Type] sur [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Page name] section.

Vous pouvez définir le nom de la page sur n’importe quelle valeur de chaîne, y compris les éléments de données.

## s.pageName dans l’éditeur de code personnalisé AppMeasurement et Lancement

La `s.pageName` variable est une chaîne qui contient généralement le nom de la page. Il a une valeur maximale de 100 octets ; les valeurs plus longues sont tronquées. Cette troncature inclut les instances auxquelles elle revient `pageURL` si cette variable est vide.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```
