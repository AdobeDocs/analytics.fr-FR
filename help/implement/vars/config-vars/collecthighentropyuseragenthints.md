---
title: collectHighEntropyUserAgentHints
description: Utilisez la variable collectHighEntropyUserAgentHints pour déterminer si Adobe va demander des indicateurs d’entropie élevée aux navigateurs Chrome et Microsoft Edge (par exemple, Google Chrome et Edge).
source-git-commit: 03d12625a0089672fa0a27f8f720065c5ca16a62
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 3%

---


# collectHighEntropyUserAgentHints

Adobe Analytics utilise des indices client à forte entropie pour améliorer l’identification des appareils et des navigateurs. En savoir plus sur les conseils aux clients dans [cette présentation et FAQ](/help/technotes/client-hints.md) ainsi que [blog Google](https://web.dev/user-agent-client-hints/).

## Collecte d’indices à forte entropie à l’aide du SDK Web

Les indicateurs client à forte entropie font partie des catégories de contexte dans le SDK Web. Voir [Configuration du SDK Web de Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=en) pour plus d’informations.

## Collecte d’indices à forte entropie à l’aide de l’extension Adobe Analytics

&quot;Collecter les indices agent-utilisateur à forte entropie&quot; est une case à cocher située sous l’accordéon Général lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [Collecte de données Adobe Experience Platform](https://experience.adobe.com/#/@adobepm/data-collection) à l’aide de vos identifiants Adobe ID.

1. Cliquez sur la [!UICONTROL propriété tag].

1. Accédez au [!UICONTROL Extensions] , puis cliquez sur [!UICONTROL Configurer] sous Adobe Analytics.

1. Développez l’objet [!UICONTROL Général] en accordéon, qui affiche la variable [!UICONTROL Collecte de conseils d’agent-utilisateur à forte entropie] . Ce paramètre est désélectionné par défaut.

## collectHighEntropyUserAgentHints dans AppMeasurement

Le `s.collectHighEntropyUserAgentHints` détermine si AppMeasurement demande des indices à forte entropie aux navigateurs Chromium (par exemple, Google Chrome et Microsoft Edge). Ces astuces sont utilisées par Adobe Analytics pour améliorer l’identification des appareils et des navigateurs.

Si cette valeur est définie sur TRUE, tous les indicateurs à forte entropie sont demandés par le navigateur.

`s.collectHighEntropyUserAgentHints = TRUE`

`s.collectHighEntropyUserAgentHints = FALSE`