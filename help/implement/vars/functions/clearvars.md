---
title: clearVars
description: Effacez les valeurs de variable de l'objet de suivi.
translation-type: tm+mt
source-git-commit: f19be69832b0a2b723d825472e0eec1e44f89440
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 95%

---


# clearVars

Certaines mises en œuvre, comme dans les applications d’une seule page, nécessitent plusieurs accès envoyés au même chargement de page. Utilisez la méthode `clearVars()` pour effacer les valeurs de variable afin qu’elles ne persistent pas dans les accès suivants.

Cette méthode ne prend aucun argument et ne renvoie aucune valeur. Son seul objectif est d’effacer les valeurs de variable de l’objet d’instance. Cette méthode définit les éléments suivants sur `undefined` :

* `prop1` - `prop75`
* `eVar` -  `eVar250`
* `hier1` -  `hier5`
* `list1` -  `list3`
* `events`
* `products`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

## Effacement des variables dans Adobe Experience Platform Launch

Définissez l’action Effacer les variables lors de la configuration d’une règle.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Effacer les variables].

## s.clearVars() dans AppMeasurement et l’éditeur de code personnalisé de Launch

Vous pouvez appeler la méthode `s.clearVars()` n’importe où dans votre mise en œuvre après avoir appelé l’instance d’objet Analytics.

```js
s.clearVars();
```
