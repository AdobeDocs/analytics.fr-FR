---
title: linkInternalFilters
description: Utilisez la variable linkInternalFilters pour faciliter le suivi automatique des liens de sortie.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkInternalFilters

AppMeasurement offre la possibilité de suivre automatiquement les liens qui renvoient en dehors de votre site. If [`trackExternalLinks`](trackexternallinks.md) is enabled, an image request is sent to Adobe right as a visitor clicks a link to leave your site. Les variables [`linkExternalFilters`](linkexternalfilters.md) et `linkInternalFilters` déterminent quels liens sont considérés comme internes/externes.

Si cette variable contient une valeur, le suivi automatique des liens de sortie se comporte comme une liste noire. Si un clic sur un lien ne correspond à aucune valeur `linkInternalFilters`, ce lien est considéré comme un lien de sortie. L’URL entière est examinée par rapport à cette variable. If [`linkLeaveQueryString`](linkleavequerystring.md) is enabled, the query string is also examined.

Si vous utilisez à la fois `linkInternalFilters` et `linkExternalFilters`, le lien sur lequel l’utilisateur a cliqué doit correspondre à `linkExternalFilters` **et** ne pas correspondre à `linkInternalFilters` pour être considéré comme un lien de sortie. Si un lien cliqué correspond à la fois aux critères de lien de sortie et de lien de téléchargement, le type de lien de téléchargement est prioritaire.

>[!NOTE] Les filtres d’URL `linkInternalFilters`[](/help/admin/admin/internal-url-filter-admin.md) et internes sont des fonctionnalités distinctes qui remplissent des fonctions distinctes. La variable `linkInternalFilters` fonctionne spécifiquement pour le suivi des liens de sortie. Les filtres d’URL internes sont un paramètre d’administration qui permet d’utiliser des dimensions de sources de trafic telles que Domaine référent.

## Liens sortants - Ne jamais effectuer le suivi dans Adobe Experience Platform Launch

The Never Track field is a comma-separated list of filters (usually domains) under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Développez l’ [!UICONTROL Link Tracking] accordéon, ce qui révèle le [!UICONTROL Outbound Links - Never Track] champ.

Placez dans ce champ des filtres que vous ne souhaitez jamais suivre comme liens de sortie. Séparez plusieurs domaines par une virgule sans espace.

## s.linkInternalFilters dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.linkInternalFilters` est une chaîne contenant des filtres (tels que les domaines) que vous considérez comme internes à votre site. Séparez plusieurs filtres à l’aide d’une virgule sans espaces.

```js
s.linkInternalFilters = "example.com,example.net,example.org";
```

Examinez l’exemple de mise en œuvre suivant comme s’il était activé `adobe.com` :

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.com">Example link 2</a>
```
