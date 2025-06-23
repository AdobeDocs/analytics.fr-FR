---
title: linkExternalFilters
description: Utilisez la variable linkExternalFilters pour faciliter le suivi automatique des liens de sortie.
feature: Appmeasurement Implementation
exl-id: 7d4e8d96-17ee-4a04-9a57-37d2056ee9a7
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 91%

---

# linkExternalFilters

AppMeasurement offre la possibilité de suivre automatiquement les liens qui renvoient en dehors de votre site. Si [`trackExternalLinks`](trackexternallinks.md) (AppMeasurement) ou [`clickCollectionEnabled`](trackexternallinks.md) (SDK Web) est activé, une demande d’image est envoyée à Adobe dès qu’un visiteur clique sur un lien pour quitter votre site. Les variables `linkExternalFilters` et [`linkInternalFilters`](linkinternalfilters.md) déterminent quels liens sont considérés comme internes/externes.

Si cette variable contient une valeur, le suivi automatique des liens de sortie se comporte comme une liste autorisée. Si un clic sur un lien ne correspond à aucune valeur `linkExternalFilters`, ce lien n’est pas considéré comme un lien de sortie. L’URL entière est examinée par rapport à cette variable. Si [`linkLeaveQueryString`](linkleavequerystring.md) est activé, la chaîne de requête est également examinée.

>[!TIP]
>
>Utilisez cette variable uniquement si vous savez exactement quels domaines vous souhaitez considérer comme des liens de sortie. De nombreuses organisations estiment que l’utilisation de `linkInternalFilters` est suffisante pour répondre à leurs besoins de suivi des liens de sortie et n’utilisent pas `linkExternalFilters`.

Si vous utilisez à la fois `linkInternalFilters` et `linkExternalFilters`, le lien sur lequel l’utilisateur a cliqué doit correspondre à `linkExternalFilters` **et** ne pas correspondre à `linkInternalFilters` pour être considéré comme un lien de sortie. Si un lien cliqué correspond à la fois aux critères de lien de sortie et de lien de téléchargement, le type de lien de téléchargement est prioritaire.

## Liens de sortie dans le SDK Web

Les liens sont automatiquement considérés comme des liens de sortie si le domaine cible du lien diffère du `window.location.hostname` actuel. Le SDK Web ne propose aucune variable de configuration permettant de modifier la détection automatique des liens de sortie. Si vous devez personnaliser les domaines considérés comme un lien de sortie, vous pouvez utiliser une logique personnalisée dans le rappel `onBeforeEventSend`.

Consultez [Suivi automatique des liens](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=fr#automaticLinkTracking) dans la documentation du SDK Web pour plus d’informations.

## Liens sortants : suivi à l’aide de l’extension Adobe Analytics

Le champ Suivi est une liste de filtres séparés par des virgules (généralement des domaines) sous l’accordéon [!UICONTROL Suivi des liens] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Suivi des liens], qui affiche le champ [!UICONTROL Liens sortants - Suivi].

Placez des filtres que vous souhaitez toujours prendre en compte comme externes dans ce champ. Séparez plusieurs domaines par une virgule sans espace.

## s.linkExternalFilters dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

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

<!-- The following link is an exit link because it matches the linkExternalFilters allowlist -->
<a href = "example.com">Example link 2</a>
```
