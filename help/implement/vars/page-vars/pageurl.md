---
title: pageURL
description: Permet de remplacer l’URL de page collectée automatiquement sur votre site.
feature: Variables
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 79%

---

# pageURL

AppMeasurement collecte automatiquement l’URL de la page dans chaque accès. Si vous souhaitez remplacer l’URL de page collectée automatiquement par AppMeasurement, vous pouvez utiliser cette variable. Dans la plupart des cas, il n’est pas nécessaire de définir cette variable.

>[!NOTE]
>
>Cette variable n’est pas une dimension disponible dans Analysis Workspace. Elle est uniquement disponible dans Data Warehouse et les flux de données. De plus, les serveurs de collecte de données d’Adobe éliminent cette dimension de toutes les demandes d’images de [suivi des liens](/help/implement/vars/functions/tl-method.md). Si vous souhaitez utiliser l’URL de la page en tant que dimension dans Analysis Workspace, ou que cette dimension soit utilisée dans les accès de suivi de liens, pensez à transmettre la variable `pageURL` dans une [eVar](evar.md) à chaque accès.

## URL de la page à l’aide du SDK Web

L’URL de la page est mappée aux variables suivantes :

* [Objet XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.URL`
* [Objet de données](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageURL` ou `data.__adobe.analytics.g`

## URL de page à l’aide de l’extension Adobe Analytics

L’extension Analytics de la collecte de données Adobe Experience Platform renseigne automatiquement l’URL de la page. Vous pouvez toutefois définir le remplacement de l’URL de la page lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet **[!UICONTROL Règles]**, puis cliquez sur une règle (ou créez une règle).
4. Sous **[!UICONTROL Actions]**, cliquez sur une action existante **[!UICONTROL Adobe Analytics - Définir des variables]** ou cliquez sur l’icône « + ».
5. Définissez la variable **[!UICONTROL Extension]** de la liste déroulante vers Adobe Analytics, et de la variable **[!UICONTROL Type d’action]** to **[!UICONTROL Définition de variables]**.
6. Recherchez la section **[!UICONTROL URL de la page]**.

Vous pouvez définir l’URL de la page sur n’importe quelle valeur de chaîne.

## s.pageURL dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

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
