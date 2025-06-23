---
title: charSet
description: La variable charSet détermine le codage utilisé par Adobe pour analyser votre demande d’image.
feature: Appmeasurement Implementation
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 65%

---

# charSet

La variable `charSet` est utilisée par Adobe pour convertir les données entrantes en UTF-8 pour le stockage et les rapports par Analytics. La plupart des sites nʼont pas besoin de définir cette variable.

Définissez cette variable uniquement si vous voyez des valeurs illisibles ([mojibake](https://fr.wikipedia.org/wiki/Mojibake)) dans les rapports. Vous pouvez définir cette variable page par page si votre site utilise différents codages sur différentes pages.

## Jeu de caractères dans le SDK Web

Actuellement, Web SDK ne prend en charge que le format UTF-8 et ne fournit pas d’options permettant de modifier le codage.

## Jeu de caractères dans l’extension Adobe Analytics

Le jeu de caractères désigne un champ sous l’accordéon [!UICONTROL Général] lors de la configuration de l’extension Adobe Analytics dans la collecte de données Adobe Experience Platform.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Général], qui affiche le champ [!UICONTROL Jeu de caractères].

Vous pouvez utiliser un jeu de caractères prédéfini ou un jeu de caractères personnalisé. Évitez de modifier la valeur `UTF-8`, sauf si vous voyez des valeurs sont illisibles dans les rapports.

## s.charSet dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `charSet` est une chaîne. Si vous avez des valeurs illisibles dans Adobe Analytics, définissez cette variable sur la même valeur que la balise HTML `<meta charset="">` de votre site.

```js
s.charSet = "UTF-8";
```
