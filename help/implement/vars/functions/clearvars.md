---
title: clearVars
description: Elle efface les valeurs suivantes de l’objet d’instance. Cette fonction supprime les éléments (en les définissant comme « undefined »).
feature: Variables
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 74%

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

## Effacement des variables à l’aide du SDK Web

Lorsque vous envoyez des données à Adobe à l’aide du SDK Web, toutes les données XDM sont effacées automatiquement.

## Effacement des variables à l’aide de l’extension Adobe Analytics

Définissez l’action Effacer les variables lors de la configuration d’une règle.

1. Connectez-vous à [Collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Effacer les variables].

## s.clearVars() dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Vous pouvez appeler la méthode `s.clearVars()` n’importe où dans votre mise en œuvre après avoir appelé l’instance d’objet Analytics.

```js
s.clearVars();
```
