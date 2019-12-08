---
description: Découvrez la variable purchaseID, qui permet d’empêcher l’affichage d’achats en double dans Adobe Analytics.
keywords: duplicate,purchase,purchaseid,s.purchaseid
subtopic: Variables
title: purchaseID
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# purchaseID

The `purchaseID` variable is used to keep an order from being counted multiple times in reporting. Whenever the purchase event is used on your site, Adobe recommends using the `purchaseID` variable.

Lorsqu’un visiteur achète un article sur votre site, `purchaseID` est généralement renseigné sur la page de remerciement ou de confirmation de commande. Définissez la `purchaseID` variable au moment du déclenchement d’un événement d’achat. Lorsque `purchaseID` est définie sur une valeur unique, les valeurs des variables de conversion ne comptent que pour les accès avec cet ID d’achat unique. La définition de la `purchaseID` variable est utile car les visiteurs mettent généralement en signet une page de confirmation d’achat à des fins personnelles. Si votre implémentation n’est pas utilisée `purchaseID`, les données de conversion (telles que les recettes) peuvent facilement gonfler lorsque les visiteurs actualisent les pages.

Outre les données d’achat, tous les événements et variables de conversion ne sont pas comptabilisés plusieurs fois pour les accès avec le même ID d’achat.

## du lien personnalisé

La `purchaseID` variable peut contenir n’importe quelle valeur alphanumérique, jusqu’à un maximum de 20 octets. Si vous définissez un ID d’achat de plus de 20 octets, la valeur est tronquée.

```js
s.purchaseID = "uniqueid";
```
