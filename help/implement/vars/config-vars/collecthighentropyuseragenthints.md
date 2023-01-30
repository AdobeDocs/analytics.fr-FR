---
title: collectHighEntropyUserAgentHints
description: Utilisez la variable collectHighEntropyUserAgentHints pour déterminer si Adobe va demander des indications à entropie élevée aux navigateurs Chromium (par exemple, Google Chrome et Microsoft Edge).
exl-id: 97cfa0f9-b35d-4c73-822f-adf30d0b7efc
source-git-commit: 5318079d6ad972e66494cd7b7f3bd64359b11012
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 82%

---

# collectHighEntropyUserAgentHints

Adobe Analytics utilise des indications du client à entropie élevée pour améliorer l’identification des appareils et des navigateurs. Cette option est disponible à partir de la version 2.23.0 du fichier AppMeasurement.js. Consultez [cette présentation et cette FAQ](/help/technotes/client-hints.md) ainsi que le [blog Google](https://web.dev/user-agent-client-hints/) pour en savoir plus sur les indications du client.

## Collecter des indications à entropie élevée en utilisant le SDK Web

Les indications du client à entropie élevée font partie des catégories de contexte dans le SDK Web. Consultez la section [Configurer le SDK Web Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=fr) pour plus d’informations.

## Collecter des indications à entropie élevée en utilisant l’extension Adobe Analytics

**[!UICONTROL Collecter des indications agent-utilisateur à entropie élevée]** est une case à cocher située sous l’accordéon Général lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à la [collecte de données Adobe Experience Platform](https://experience.adobe.com/#/@adobepm/data-collection) à l’aide de vos identifiants Adobe ID.

1. Cliquez sur la [!UICONTROL propriété de balise] de votre choix.

1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur [!UICONTROL Configurer] sous Adobe Analytics.

1. Développez l’accordéon [!UICONTROL Général], qui affiche la case à cocher [!UICONTROL Collecter des indications agent-utilisateur à entropie élevée]. Cette case est désactivée par défaut.

## collectHighEntropyUserAgentHints dans AppMeasurement

Le `s.collectHighEntropyUserAgentHints` détermine si AppMeasurement demande des conseils à forte entropie aux navigateurs Chromium (par exemple, Google Chrome ou Microsoft Edge). Adobe Analytics utilise ces indications pour améliorer l’identification des appareils et des navigateurs.

Si la variable est définie sur `true`, tous les indices à forte entropie seront demandés au navigateur.

```js
s.collectHighEntropyUserAgentHints = true;
```
