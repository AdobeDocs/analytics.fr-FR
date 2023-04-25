---
title: channel
description: Permet de renseigner la dimension « Sections du site ».
feature: Variables
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 77%

---

# channel

La variable `channel` stocke généralement la section du site sur laquelle se trouve une page donnée. Il est utile de déterminer les groupes de votre site les plus populaires. Cette variable renseigne la dimension Sections du site.

## Canal utilisant le SDK Web

Le canal est [mappé pour Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=fr) sous le champ XDM `web.webPageDetails.siteSection`.

## Canal utilisant l’extension Adobe Analytics

Vous pouvez définir le canal soit lors de la configuration de l’extension Analytics (variables globales), soit sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la variable [!UICONTROL Extension] de la liste déroulante vers Adobe Analytics, et la variable [!UICONTROL Type d’action] to [!UICONTROL Définition de variables].
6. Recherchez la section [!UICONTROL Canal].

Vous pouvez définir le canal sur n’importe quelle valeur de chaîne ou élément de données.

## s.channel dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.channel` est une chaîne qui contient généralement la section du site de la page. Celle-ci a une valeur maximale de 100 octets ; les valeurs plus longues sont tronquées.

```js
s.channel = "Example site section";
```

Si vous utilisez la `digitalData` [couche de données](../../prepare/data-layer.md) :

```js
s.channel = digitalData.page.category.primaryCategory;
```
