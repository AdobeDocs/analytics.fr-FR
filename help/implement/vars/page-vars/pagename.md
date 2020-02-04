---
title: pageName
description: Nom de la page de votre site.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# pageName

La `pageName` variable stocke généralement le nom d’une page donnée. Il est utile de déterminer les pages les plus populaires. Cette variable renseigne la dimension &quot;Nom de page&quot;.

> [!NOTE] Cette dimension est toujours supprimée des appels de suivi de liens. Si vous souhaitez voir le nom de la page sur laquelle un lien a été suivi, pensez à copier cette variable dans une eVar.

Si cette variable n’est pas définie sur un appel de suivi de page donné, la `pageURL` variable est utilisée à la place.

## Nom de page dans Adobe Experience Platform Launch

Vous pouvez définir le nom de la page lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Règles] , puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le type [!UICONTROL d’] action sur [!UICONTROL Définir des variables].
6. Recherchez la section du nom [!UICONTROL de la] page.

Vous pouvez définir le nom de la page sur n’importe quelle valeur de chaîne, y compris les éléments de données.

## s.pageName dans l’éditeur de code personnalisé AppMeasurement et Lancement

La `s.pageName` variable est une chaîne qui contient généralement le nom de la page. Il a une valeur maximale de 100 octets ; les valeurs plus longues sont tronquées. Cette troncature inclut les instances auxquelles elle revient `pageURL` si cette variable est vide.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```
