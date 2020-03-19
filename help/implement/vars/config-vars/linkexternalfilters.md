---
title: linkExternalFilters
description: Utilisez la variable linkExternalFilters pour faciliter le suivi automatique des liens de sortie.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkExternalFilters

AppMeasurement  la capacité de suivre automatiquement les liens qui pointent en dehors de votre site. Si [`trackExternalLinks`](trackexternallinks.md) est activé, une demande d’image est envoyée à Adobe à droite lorsqu’un clique sur un lien pour quitter votre site. Les `linkExternalFilters` variables et [`linkInternalFilters`](linkinternalfilters.md) les variables déterminent quels liens sont considérés comme internes/externes.

Si cette variable contient une valeur, le suivi automatique des liens de sortie se comporte comme une liste blanche. Si un clic sur un lien ne correspond à aucune `linkExternalFilters` valeur, il n’est pas considéré comme un lien de sortie. L’URL entière est examinée par rapport à cette variable. Si [`linkLeaveQueryString`](linkleavequerystring.md) est activé, la chaîne de  du est également examinée.

> [!TIP] Utilisez cette variable uniquement si vous savez exactement quels domaines vous souhaitez considérer comme des liens de sortie. De nombreuses organisations estiment que l’utilisation `linkInternalFilters` est suffisante pour répondre à leurs besoins de suivi des liens de sortie et ne l’utilisent pas `linkExternalFilters`.

Si vous utilisez à la fois `linkInternalFilters` et `linkExternalFilters` simultanément, le lien sur lequel l’utilisateur a cliqué doit correspondre `linkExternalFilters` et ne pas correspondre **** `linkInternalFilters` pour être considéré comme un lien de sortie. Si un lien cliqué correspond à la fois aux critères de lien de sortie et de lien de téléchargement, le type de lien de téléchargement est prioritaire.

## Liens sortants - Suivi dans le lancement d’Adobe Experience Platform

Le champ de suivi est un d’ (généralement des domaines) séparés par des virgules sous l’ [!UICONTROL Link Tracking] accordéon lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Configure] bouton sous Adobe Analytics.
4. Développez l’ [!UICONTROL Link Tracking] accordéon, ce qui révèle le [!UICONTROL Outbound Links - Track] champ.

Placez  que vous souhaitez toujours considérer comme externe dans ce champ. Séparez plusieurs domaines par une virgule sans espace.

## s.linkExternalFilters dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.linkExternalFilters` variable est une chaîne contenant des  de (tels que des domaines) que vous considérez comme des liens de sortie. Séparez plusieurs domaines à l’aide d’une virgule sans espaces.

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

Examinez l’exemple d’implémentation suivant comme s’il était activé `adobe.com`:

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
