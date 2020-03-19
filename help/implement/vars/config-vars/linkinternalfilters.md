---
title: linkInternalFilters
description: Utilisez la variable linkInternalFilters pour faciliter le suivi automatique des liens de sortie.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkInternalFilters

AppMeasurement  la capacité de suivre automatiquement les liens qui pointent en dehors de votre site. Si [`trackExternalLinks`](trackexternallinks.md) est activé, une demande d’image est envoyée à Adobe à droite lorsqu’un clique sur un lien pour quitter votre site. Les [`linkExternalFilters`](linkexternalfilters.md) variables et `linkInternalFilters` les variables déterminent quels liens sont considérés comme internes/externes.

Si cette variable contient une valeur, le suivi automatique des liens de sortie se comporte comme une liste noire. Si un clic sur un lien ne correspond à aucune `linkInternalFilters` valeur, il est considéré comme un lien de sortie. L’URL entière est examinée par rapport à cette variable. Si [`linkLeaveQueryString`](linkleavequerystring.md) est activé, la chaîne de  du est également examinée.

Si vous utilisez à la fois `linkInternalFilters` et `linkExternalFilters` simultanément, le lien sur lequel l’utilisateur a cliqué doit correspondre `linkExternalFilters` et ne pas correspondre **** `linkInternalFilters` pour être considéré comme un lien de sortie. Si un lien cliqué correspond à la fois aux critères de lien de sortie et de lien de téléchargement, le type de lien de téléchargement est prioritaire.

> [!NOTE] Les `linkInternalFilters` URL [internes et les](/help/admin/admin/internal-url-filter-admin.md) URL internes sont des fonctionnalités distinctes qui remplissent des objectifs distincts. La `linkInternalFilters` variable fonctionne spécifiquement pour le suivi des liens de sortie. Les  d’URL internes sont un paramètre d’administration qui permet d’utiliser les dimensions des sources de trafic telles que Domaine référent.

## Liens sortants - Ne jamais effectuer le suivi dans le lancement d’Adobe Experience Platform

Le champ Ne jamais effectuer le suivi est un de  de (généralement des domaines) séparé par des virgules sous l’ [!UICONTROL Link Tracking] accordéon lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Configure] bouton sous Adobe Analytics.
4. Développez l’ [!UICONTROL Link Tracking] accordéon, ce qui révèle le [!UICONTROL Outbound Links - Never Track] champ.

Placez  que vous ne souhaitez jamais faire l’objet d’un suivi en tant que liens de sortie dans ce champ. Séparez plusieurs domaines par une virgule sans espace.

## s.linkInternalFilters dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.linkInternalFilters` variable est une chaîne contenant des  (tels que des domaines) que vous considérez comme internes à votre site. Séparez plusieurs à l’aide d’une virgule sans espaces.

```js
s.linkInternalFilters = "example.com,example.net,example.org";
```

Examinez l’exemple d’implémentation suivant comme s’il était activé `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.com">Example link 2</a>
```
