---
title: pageURL
description: Permet de remplacer l’URL de page collectée automatiquement sur votre site.
feature: Appmeasurement Implementation
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
role: Admin, Developer
TQID: https://experienceleague.adobe.com/DZM2tZlfVX0g9OYMj6tPFuHInBZdBrboJ4vGz16Lfrs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 310
ht-degree: 84%

---

# pageURL

AppMeasurement collecte automatiquement l’URL de la page dans chaque accès. Si vous souhaitez remplacer l’URL de page collectée automatiquement par AppMeasurement, vous pouvez utiliser cette variable. Dans la plupart des cas, il n’est pas nécessaire de définir cette variable.

>[!NOTE]
>
>Cette variable n’est pas une dimension disponible dans Analysis Workspace. Elle est uniquement disponible dans Data Warehouse et les flux de données. De plus, les serveurs de collecte de données d’Adobe éliminent cette dimension de toutes les demandes d’images de [suivi des liens](/help/implement/vars/functions/tl-method.md). Si vous souhaitez utiliser l’URL de la page en tant que dimension dans Analysis Workspace, ou que cette dimension soit utilisée dans les accès de suivi de liens, pensez à transmettre la variable `pageURL` dans une [eVar](evar.md) à chaque accès.

## URL de la page utilisant le SDK Web

L’URL de la page est mappée aux variables suivantes :

* [Objet XDM](/help/implement/aep-edge/xdm-var-mapping.md) : `xdm.web.webPageDetails.URL`
* [Objet de données](/help/implement/aep-edge/data-var-mapping.md) : `data.__adobe.analytics.pageURL` ou `data.__adobe.analytics.g`

## URL de la page utilisant l’extension Adobe Analytics

L’extension Analytics dans la collecte de données Adobe Experience Platform renseigne automatiquement l’URL de la page. Vous pouvez toutefois définir le remplacement de l’URL de la page lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet **[!UICONTROL Règles]**, puis cliquez sur une règle (ou créez une règle).
4. Sous **[!UICONTROL Actions]**, cliquez sur une action existante **[!UICONTROL Adobe Analytics - Définir des variables]** ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante **[!UICONTROL Extension]** sur Adobe Analytics et le **[!UICONTROL type d’action]** sur **[!UICONTROL Définir des variables]**.
6. Recherchez la section **[!UICONTROL URL de la page]**.

Vous pouvez définir l’URL de la page sur n’importe quelle valeur de chaîne.

## s.pageURL dans AppMeasurement et éditeur de code personnalisé de l’extension Analytics

La variable `s.pageURL` est une chaîne qui contient l’URL de la page. AppMeasurement collecte automatiquement cette variable, mais vous pouvez remplacer sa valeur si vous le souhaitez.

```js
s.pageURL = "https://example.com";
```

Si vous souhaitez utiliser l’URL de page comme dimension dans les rapports, pensez à utiliser les éléments suivants dans votre mise en œuvre :

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

Si vous utilisez la `digitalData` [couche de données](../../prepare/data-layer.md) :

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
