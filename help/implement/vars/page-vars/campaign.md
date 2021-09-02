---
title: campaign
description: Permet de renseigner la dimension « Code de suivi ».
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '195'
ht-degree: 100%

---

# campaign

La variable `campaign` est dédiée à la collecte des codes de suivi sur votre site. Dans les versions précédentes d’Adobe Analytics, celle-ci bénéficiait d’un traitement spécial où elle pouvait être utilisée comme ventilation pour la plupart des dimensions. Dans la version actuelle d’Adobe Analytics, elle agit de la même manière qu’une eVar.

Cette variable renseigne la dimension « Code de suivi ».

## Campagne à l’aide de balises dans Adobe Experience Platform

Vous pouvez définir la campagne soit lors de la configuration de l’extension Analytics (variables globales), soit sous des règles.

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Campagne].

Vous pouvez définir la campagne sur une valeur ou un paramètre de chaîne de requête.

## s.campaign dans AppMeasurement et l’éditeur de code personnalisé

La variable `s.campaign` est une chaîne qui contient généralement un code de suivi utilisé dans les actions marketing. Sa longueur maximale est de 255 octets ; les valeurs de plus de 255 octets sont automatiquement tronquées lorsqu’elles sont envoyées à Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
