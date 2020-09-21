---
title: channel
description: Permet de renseigner la dimension « Sections du site ».
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 97%

---


# channel

La variable `channel` stocke généralement la section du site sur laquelle se trouve une page donnée. Il est utile de déterminer les groupes de votre site les plus populaires. Cette variable renseigne la dimension Sections du site.

## Canal dans Adobe Experience Platform Launch

Vous pouvez définir le canal soit lors de la configuration de l’extension Analytics (variables globales), soit sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Canal].

Vous pouvez définir le canal sur n’importe quelle valeur de chaîne ou élément de données.

## s.channel dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.channel` est une chaîne qui contient généralement la section du site de la page. Celle-ci a une valeur maximale de 100 octets ; les valeurs plus longues sont tronquées.

```js
s.channel = "Example site section";
```

Si vous utilisez la couche `digitalData` de [](../../prepare/data-layer.md)données :

```js
s.channel = digitalData.page.category.primaryCategory;
```
