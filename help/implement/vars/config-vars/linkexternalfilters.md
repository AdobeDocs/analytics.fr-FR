---
title: linkExternalFilters
description: Utilisez la variable linkExternalFilters pour faciliter le suivi automatique des liens de sortie.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkExternalFilters

AppMeasurement offre la possibilité de suivre automatiquement les liens qui renvoient en dehors de votre site. If [`trackExternalLinks`](trackexternallinks.md) is enabled, an image request is sent to Adobe right as a visitor clicks a link to leave your site. Les variables `linkExternalFilters` et [`linkInternalFilters`](linkinternalfilters.md) déterminent quels liens sont considérés comme internes/externes.

Si cette variable contient une valeur, le suivi automatique des liens de sortie se comporte comme une liste blanche. Si un clic sur un lien ne correspond à aucune valeur `linkExternalFilters`, ce lien n’est pas considéré comme un lien de sortie. L’URL entière est examinée par rapport à cette variable. If [`linkLeaveQueryString`](linkleavequerystring.md) is enabled, the query string is also examined.

>[!TIP] Utilisez cette variable uniquement si vous savez exactement quels domaines vous souhaitez considérer comme des liens de sortie. De nombreuses organisations estiment que l’utilisation de `linkInternalFilters` est suffisante pour répondre à leurs besoins de suivi des liens de sortie et n’utilisent pas `linkExternalFilters`.

Si vous utilisez à la fois `linkInternalFilters` et `linkExternalFilters`, le lien sur lequel l’utilisateur a cliqué doit correspondre à `linkExternalFilters` **et** ne pas correspondre à `linkInternalFilters` pour être considéré comme un lien de sortie. Si un lien cliqué correspond à la fois aux critères de lien de sortie et de lien de téléchargement, le type de lien de téléchargement est prioritaire.

## Liens sortants - Suivi dans Adobe Experience Platform Launch

Le champ Suivi est une liste de filtres séparés par des virgules (généralement des domaines) sous l’accordéon [!UICONTROL Suivi des liens] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Suivi des liens], qui affiche le champ [!UICONTROL Liens sortants - Suivi].

Placez des filtres que vous souhaitez toujours prendre en compte comme externes dans ce champ. Séparez plusieurs domaines par une virgule sans espace.

## s.linkExternalFilters dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.linkExternalFilters` est une chaîne contenant des filtres (tels que les domaines) que vous considérez comme des liens de sortie. Séparez plusieurs domaines à l’aide d’une virgule sans espaces.

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

Examinez l’exemple de mise en œuvre suivant comme s’il était activé `adobe.com` :

```html
<script>
  s.trackExternalLinks = true;
  s.linkExternalFilters = "example.com,example.net";
</script>

<!-- The following link is NOT considered an exit link, even though the link is outside adobe.com -->
<a href = "example.org">Example link 1</a>

<!-- The following link is an exit link because it matches the linkExternalFilters whitelist -->
<a href = "example.com">Example link 2</a>
```
