---
title: charSet
description: La variable charSet détermine le codage utilisé par Adobe pour analyser votre demande d’image.
feature: Variables
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
source-git-commit: ef82c34f97a0c8172f097b83b521860a1897c82c
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 66%

---

# charSet

Le `charSet` est utilisée par Adobe pour convertir les données entrantes au format UTF-8 pour le stockage et la création de rapports par Analytics. La plupart des sites nʼont pas besoin de définir cette variable.

Définissez cette variable uniquement si vous voyez des valeurs illisibles ([mojibake](https://fr.wikipedia.org/wiki/Mojibake)) dans les rapports. Vous pouvez définir cette variable page par page si votre site utilise différents codages sur différentes pages.

## Jeu de caractères dans le SDK Web

Actuellement, le SDK Web ne prend en charge que le codage UTF-8 et ne fournit pas d’options pour modifier le codage.

## Jeu de caractères dans l’extension Adobe Analytics

Un jeu de caractères est un champ situé sous le [!UICONTROL Général] lors de la configuration de l’extension Adobe Analytics dans la collecte de données Adobe Experience Platform.

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
