---
title: campaign
description: Permet de renseigner la dimension « Code de suivi ».
feature: Appmeasurement Implementation
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
role: Admin, Developer
TQID: https://experienceleague.adobe.com/01o3kclFhTclLelfDNUPI0zNTQO0X-ijCQ37RtrGsvA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 244
ht-degree: 74%

---

# campaign

La variable `campaign` est dédiée à la collecte des codes de suivi sur votre site. Dans les versions précédentes d’Adobe Analytics, celle-ci bénéficiait d’un traitement spécial où elle pouvait être utilisée comme répartition pour la plupart des dimensions. Dans la version actuelle d’Adobe Analytics, elle agit de la même manière qu’une eVar.

Cette variable renseigne la dimension [Code de suivi](/help/components/dimensions/tracking-code.md). Elle obtient généralement sa valeur à partir d’une chaîne de requête à l’aide de la méthode de l’utilitaire [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md). Cependant, votre entreprise détermine exactement comment définir cette variable.

## Campagne à l’aide de Web SDK

Campaign est mappé sur les variables suivantes :

* [Objet XDM](/help/implement/aep-edge/xdm-var-mapping.md) : `marketing.trackingCode`
* [Objet de données](/help/implement/aep-edge/data-var-mapping.md) : `data.__adobe.analytics.campaign` ou `data.__adobe.analytics.v0`

## Campagne utilisant l’extension Adobe Analytics

Vous pouvez définir la campagne soit lors de la configuration de l’extension Analytics (variables globales), soit sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Définir des variables].
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
