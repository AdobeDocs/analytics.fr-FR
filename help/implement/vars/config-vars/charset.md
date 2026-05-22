---
title: charSet
description: La variable charSet détermine le codage utilisé par Adobe pour analyser votre demande d’image.
feature: Appmeasurement Implementation
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/bPK-uLu-IgKnJWGpAUnS7cmRm808jhetzm-Cyd2R39o'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 235
ht-degree: 66%

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
