---
title: linkInternalFilters
description: Utilisez la variable linkInternalFilters pour faciliter le suivi automatique des liens de sortie.
feature: Appmeasurement Implementation
exl-id: eaa6e64a-ebd5-4e6b-913f-1a6c315579c8
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 100%

---

# linkInternalFilters

AppMeasurement offre la possibilité de suivre automatiquement les liens qui renvoient en dehors de votre site. Si [`trackExternalLinks`](trackexternallinks.md) (AppMeasurement) ou [`clickCollectionEnabled`](trackdownloadlinks.md) (SDK Web) est activé, une demande d’image est envoyée à Adobe dès qu’un visiteur clique sur un lien pour quitter votre site. Les variables [`linkExternalFilters`](linkexternalfilters.md) et `linkInternalFilters` déterminent quels liens sont considérés comme internes/externes.

Si cette variable contient une valeur, le suivi automatique des liens de sortie se comporte comme une liste bloquée. Si un clic sur un lien ne correspond à aucune valeur `linkInternalFilters`, ce lien est considéré comme un lien de sortie. L’URL entière est examinée par rapport à cette variable. Si [`linkLeaveQueryString`](linkleavequerystring.md) est activé, la chaîne de requête est également examinée.

Si vous utilisez à la fois `linkInternalFilters` et `linkExternalFilters`, le lien sur lequel l’utilisateur a cliqué doit correspondre à `linkExternalFilters` **et** ne pas correspondre à `linkInternalFilters` pour être considéré comme un lien de sortie. Si un lien cliqué correspond à la fois aux critères de lien de sortie et de lien de téléchargement, le type de lien de téléchargement est prioritaire.

Activity Map utilise cette variable pour aider à déterminer quels liens sont internes à votre site. Adobe recommande de définir cette variable pour les mises en œuvre qui utilisent Activity Map.

>[!NOTE]
>
>`linkInternalFilters` et les [filtres d’URL internes](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) sont des fonctionnalités distinctes qui remplissent des fonctions distinctes. La variable `linkInternalFilters` fonctionne spécifiquement pour le suivi des liens de sortie. Les filtres d’URL internes sont un paramètre d’administration qui permet d’utiliser des dimensions de sources de trafic telles que Domaine référent.

## Liens de sortie dans le SDK Web

Les liens sont automatiquement considérés comme des liens de sortie si le domaine cible du lien diffère du `window.location.hostname` actuel. Le SDK Web ne propose aucune variable de configuration permettant de modifier la détection automatique des liens de sortie. Si vous devez personnaliser les domaines considérés comme un lien de sortie, vous pouvez utiliser une logique personnalisée dans le rappel `onBeforeEventSend`.

Consultez [Suivi automatique des liens](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=fr#automaticLinkTracking) dans la documentation du SDK Web pour plus d’informations.

## Liens sortants - Ne jamais effectuer le suivi à l’aide de l’extension Adobe Analytics

Le champ Ne jamais suivre est une liste de filtres séparés par des virgules (généralement des domaines) sous l’accordéon [!UICONTROL Suivi des liens] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Suivi des liens], qui affiche le champ [!UICONTROL Liens sortants - Ne jamais suivre].

Placez dans ce champ des filtres que vous ne souhaitez jamais suivre comme liens de sortie. Séparez plusieurs domaines par une virgule sans espace.

## s.linkInternalFilters dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.linkInternalFilters` est une chaîne contenant des filtres (tels que les domaines) que vous considérez comme internes à votre site. Séparez plusieurs filtres à l’aide d’une virgule sans espaces.

```js
s.linkInternalFilters = "example.com,example.net";
```

Examinez l’exemple de mise en œuvre suivant comme s’il était activé `adobe.com` :

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.org">Example link 2</a>
```
