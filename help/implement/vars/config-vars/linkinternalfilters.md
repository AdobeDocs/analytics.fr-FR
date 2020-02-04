---
title: linkInternalFilters
description: Utilisez la variable linkInternalFilters pour faciliter le suivi automatique des liens de sortie.
translation-type: tm+mt
source-git-commit: 8f7baa770f800ffe800e760f1eca59911d3db348

---


# linkInternalFilters

AppMeasurement offre la possibilité de suivre automatiquement les liens qui pointent en dehors de votre site. Si `trackExternalLinks` est `true`le cas, une demande d’image est envoyée à Adobe dès qu’un visiteur clique sur un lien pour quitter votre site. Les `linkTrackExternalFilters` variables et `linkTrackInternalFilters` les variables déterminent quels liens sont considérés comme internes/externes.

Si cette variable contient une valeur, le suivi automatique des liens de sortie se comporte comme une liste noire. Si un clic sur un lien ne correspond à aucune `linkInternalFilters` valeur, il est considéré comme un lien de sortie. L’URL entière est examinée par rapport à cette variable. Si `linkLeaveQueryString` est `true`, la chaîne de requête est également examinée.

Si vous utilisez à la fois `linkInternalFilters` et `linkExternalFilters` simultanément, le lien sur lequel l’utilisateur a cliqué doit correspondre `linkExternalFilters` et ne pas correspondre **** `linkInternalFilters` pour être considéré comme un lien de sortie. Si un lien cliqué correspond à la fois aux critères de lien de sortie et de lien de téléchargement, le type de lien de téléchargement est prioritaire.

> [!NOTE] Les filtres d’URL `linkInternalFilters` et internes sont des fonctionnalités distinctes qui remplissent des fonctions distinctes. La `linkInternalFilters` variable fonctionne spécifiquement pour le suivi des liens de sortie. Les filtres d’URL internes sont un paramètre d’administration qui permet d’utiliser des dimensions de sources de trafic telles que Domaine référent. See [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md) in the Admin user guide.

## Liens sortants - Ne jamais effectuer le suivi dans le lancement d’Adobe Experience Platform

Le champ Ne jamais suivre est une liste de filtres séparés par des virgules (généralement des domaines) sous l’accordéon Suivi des [!UICONTROL liens] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon Suivi des [!UICONTROL liens] , qui affiche le champ Liens [!UICONTROL sortants - Ne jamais suivre] .

Placez dans ce champ des filtres que vous ne souhaitez jamais suivre comme liens de sortie. Séparez plusieurs domaines par une virgule sans espace.

## s.linkInternalFilters dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.linkInternalFilters` variable est une chaîne contenant des filtres (tels que les domaines) que vous considérez comme internes à votre site. Séparez plusieurs filtres à l’aide d’une virgule sans espaces.

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
