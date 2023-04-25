---
title: campaign
description: Permet de renseigner la dimension « Code de suivi ».
feature: Variables
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 68%

---

# campaign

La variable `campaign` est dédiée à la collecte des codes de suivi sur votre site. Dans les versions précédentes d’Adobe Analytics, celle-ci bénéficiait d’un traitement spécial où elle pouvait être utilisée comme ventilation pour la plupart des dimensions. Dans la version actuelle d’Adobe Analytics, elle agit de la même manière qu’une eVar.

Cette variable renseigne la variable [Code de suivi](/help/components/dimensions/tracking-code.md) dimension. Elle obtient généralement sa valeur à partir d’une chaîne de requête à l’aide de la variable [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) Utilitaire . Cependant, votre entreprise détermine exactement comment définir cette variable.

## Campaign à l&#39;aide du SDK Web

Campaign est [mappé pour Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=fr) sous le champ XDM `marketing.trackingCode`.

## Campaign à l’aide de l’extension Adobe Analytics

Vous pouvez définir la campagne soit lors de la configuration de l’extension Analytics (variables globales), soit sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la variable [!UICONTROL Extension] de la liste déroulante vers Adobe Analytics, et la variable [!UICONTROL Type d’action] to [!UICONTROL Définition de variables].
6. Recherchez la section [!UICONTROL Campagne].

Vous pouvez définir la campagne sur une valeur ou un paramètre de chaîne de requête.

## s.campaign dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.campaign` est une chaîne qui contient généralement un code de suivi utilisé dans les actions marketing. Sa longueur maximale est de 255 octets ; les valeurs de plus de 255 octets sont automatiquement tronquées lorsqu’elles sont envoyées à Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
