---
title: clearVars
description: Elle efface les valeurs suivantes de l’objet d’instance. Cette fonction supprime les éléments (en les définissant comme « undefined »).
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# clearVars

Certaines implémentations, comme dans les applications d’une seule page, nécessitent plusieurs accès envoyés au même chargement de page. Utilisez la `clearVars()` méthode pour effacer les valeurs de variable afin qu’elles ne persistent pas dans les accès suivants.

Cette méthode ne prend aucun argument et ne renvoie aucune valeur. Son seul objectif est d’effacer les valeurs de variable de l’objet d’instance. Cette méthode définit les éléments suivants sur `undefined`:

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

## Effacer les variables dans le lancement d’Adobe Experience Platform

Définissez l’action Effacer les variables lors de la configuration d’une règle.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Rules] onglet, puis cliquez sur la règle souhaitée (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur l’icône &quot;+&quot;
5. Définissez la [!UICONTROL Extension] liste déroulante sur Adobe Analytics et la [!UICONTROL Action Type] sur [!UICONTROL Clear Variables].

## s.clearVars() dans l’éditeur de code personnalisé AppMeasurement et de lancement

Vous pouvez appeler la `s.clearVars()` méthode n’importe où dans votre implémentation après avoir instancié l’instance d’objet Analytics.

```js
s.clearVars();
```
