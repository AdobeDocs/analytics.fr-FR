---
title: pageURL
description: Permet de remplacer l’URL de page collectée automatiquement sur votre site.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 81%

---


# pageURL

AppMeasurement collecte automatiquement l’URL de la page dans chaque accès. Si vous souhaitez remplacer l’URL de page collectée automatiquement par AppMeasurement, vous pouvez utiliser cette variable. Dans la plupart des cas, il n’est pas nécessaire de définir cette variable.

>[!NOTE]
>
>Cette variable n’est pas une dimension disponible dans Analysis Workspace. Elle est uniquement disponible dans Data Warehouse et les flux de données. En outre, les serveurs de collecte de données d’Adobe éliminent cette dimension de toutes les demandes d’image de suivi [de](/help/implement/vars/functions/tl-method.md) liens. Si vous souhaitez utiliser l’URL de page comme dimension en Analysis Workspace ou que cette dimension doit être utilisée dans les accès de suivi de liens, pensez à transmettre la `pageURL` variable dans un [eVar](evar.md) pour chaque accès.

## URL de page dans Adobe Experience Platform Launch

Launch renseigne automatiquement l’URL de la page. Vous pouvez toutefois définir le remplacement de l’URL de la page lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet **[!UICONTROL Règles]**, puis cliquez sur une règle (ou créez une règle).
4. Sous **[!UICONTROL Actions]**, cliquez sur une action existante **[!UICONTROL Adobe Analytics - Définir des variables]** ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante **[!UICONTROL Extension]** sur Adobe Analytics et le **[!UICONTROL type d’action]** sur **[!UICONTROL Définir des variables]**.
6. Recherchez la section **[!UICONTROL URL de la page]**.

Vous pouvez définir l’URL de la page sur n’importe quelle valeur de chaîne.

## s.pageURL dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.pageURL` est une chaîne qui contient l’URL de la page. AppMeasurement collecte automatiquement cette variable, mais vous pouvez remplacer sa valeur si vous le souhaitez.

```js
s.pageURL = "https://example.com";
```

Si vous souhaitez utiliser l’URL de page comme dimension dans les rapports, pensez à utiliser les éléments suivants dans votre mise en œuvre :

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

Si vous utilisez la couche `digitalData` de [](../../prepare/data-layer.md)données :

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
