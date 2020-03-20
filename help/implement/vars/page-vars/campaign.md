---
title: campaign
description: Permet de renseigner la dimension « Code de suivi ».
translation-type: tm+mt
source-git-commit: 7220b99268532adb2e425d52744dbc3efb615953

---


# campaign

La variable `campaign` est dédiée à la collecte des codes de suivi sur votre site. Dans les versions précédentes d’Adobe Analytics, celle-ci bénéficiait d’un traitement spécial où elle pouvait être utilisée comme ventilation pour la plupart des dimensions. Dans la version actuelle d’Adobe Analytics, elle agit de la même manière qu’une eVar.

Cette variable renseigne la dimension « Code de suivi ».

## Campaign dans Adobe Experience Platform Launch

Vous pouvez définir la campagne soit lors de la configuration de l’extension Analytics (variables globales), soit sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Sous [!UICONTROL Actions], cliquez sur une [!UICONTROL Adobe Analytics - Set Variables] action existante ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la [!UICONTROL Extension] liste déroulante sur Adobe Analytics et la [!UICONTROL Action Type] sur [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Campaign] section.

Vous pouvez définir la campagne sur une valeur ou un paramètre de chaîne de requête.

## s.campaign dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.campaign` est une chaîne qui contient généralement un code de suivi utilisé dans les actions marketing. Sa longueur maximale est de 255 octets ; les valeurs de plus de 255 octets sont automatiquement tronquées lorsqu’elles sont envoyées à Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
