---
title: pageURL
description: Permet de remplacer l’URL de page collectée automatiquement sur votre site.
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '279'
ht-degree: 100%

---

# pageURL

AppMeasurement collecte automatiquement l’URL de la page dans chaque accès. Si vous souhaitez remplacer l’URL de page collectée automatiquement par AppMeasurement, vous pouvez utiliser cette variable. Dans la plupart des cas, il n’est pas nécessaire de définir cette variable.

>[!NOTE]
>
>Cette variable n’est pas une dimension disponible dans Analysis Workspace. Elle est uniquement disponible dans Data Warehouse et les flux de données. De plus, les serveurs de collecte de données d’Adobe éliminent cette dimension de toutes les demandes d’images de [suivi des liens](/help/implement/vars/functions/tl-method.md). Si vous souhaitez utiliser l’URL de la page en tant que dimension dans Analysis Workspace, ou que cette dimension soit utilisée dans les accès de suivi de liens, pensez à transmettre la variable `pageURL` dans une [eVar](evar.md) à chaque accès.

## URL de page à l’aide de balises dans Adobe Experience Platform

L’interface utilisateur de la collecte de données renseigne automatiquement l’URL de page. Vous pouvez toutefois définir le remplacement de l’URL de la page lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet **[!UICONTROL Règles]**, puis cliquez sur une règle (ou créez une règle).
4. Sous **[!UICONTROL Actions]**, cliquez sur une action existante **[!UICONTROL Adobe Analytics - Définir des variables]** ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante **[!UICONTROL Extension]** sur Adobe Analytics et le **[!UICONTROL type d’action]** sur **[!UICONTROL Définir des variables]**.
6. Recherchez la section **[!UICONTROL URL de la page]**.

Vous pouvez définir l’URL de la page sur n’importe quelle valeur de chaîne.

## s.pageURL dans AppMeasurement et l’éditeur de code personnalisé

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
