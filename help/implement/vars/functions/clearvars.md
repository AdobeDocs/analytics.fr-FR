---
title: clearVars
description: Effacez les valeurs de l’objet d’instance.
feature: Appmeasurement Implementation
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 67%

---

# clearVars

Certaines mises en œuvre, comme dans les applications d’une seule page, nécessitent plusieurs accès envoyés au même chargement de page. Utilisez la méthode `clearVars()` pour effacer les valeurs de variable afin qu’elles ne persistent pas dans les accès suivants.

Cette méthode ne prend aucun argument et ne renvoie aucune valeur. Son seul objectif est d’effacer les valeurs de variable de l’objet d’instance. Cette méthode définit les éléments suivants sur `undefined` :

* `prop1` - `prop75`
* `eVar` - `eVar250`
* `hier1` - `hier5`
* `list1` - `list3`
* `events`
* `products`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

## Effacer des variables à l’aide de Web SDK

Lorsque vous envoyez des données à Adobe à l’aide de Web SDK, toutes les données XDM sont automatiquement effacées.

## Effacer des variables à l’aide de l’extension Adobe Analytics

Définissez l’action Effacer les variables lors de la configuration d’une règle.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics, et le [!UICONTROL Type d’action] sur [!UICONTROL Effacer les variables].

## s.clearVars() dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Vous pouvez appeler la méthode `s.clearVars()` n’importe où dans votre mise en œuvre après avoir appelé l’instance d’objet Analytics.

```js
s.clearVars();
```
