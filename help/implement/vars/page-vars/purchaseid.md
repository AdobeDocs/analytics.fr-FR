---
title: purchaseID
description: permet de dédupliquer les accès en fonction d’un identifiant d’achat unique.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# purchaseID

La `purchaseID` variable permet d’empêcher les accès contenant le même achat de gonfler les rapports. Par exemple, si un visiteur accède à votre page de confirmation d’achat, vous envoyez généralement des données sur les recettes générées par la transaction à Adobe. Si l’utilisateur actualise cette page plusieurs fois ou signets la page à consulter ultérieurement, ces accès peuvent gonfler les rapports. La `purchaseID` variable déduplique les mesures lorsque plusieurs accès ont le même ID d’achat.

Lorsqu’Adobe reconnaît un accès comme un achat en double, toutes les données de conversion (telles que les eVars et les événements) ne s’affichent pas dans les rapports. Dans les flux de données, la `duplicate_purchase` colonne est définie sur `1`.

Les ID d’achat s’appliquent à tous les visiteurs et n’expirent pas. Si un visiteur définit un ID d’achat donné, puis un autre visiteur définit le même ID d’achat un an plus tard, le second achat est dédupliqué.

## ID d’achat dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.purchaseID dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.purchaseID` variable est une chaîne qui contient un identifiant unique pour un achat. Il est défini sur le même accès qu’un événement d’achat. Utilisez uniquement des caractères alphanumériques pour renseigner cette variable.

Cette variable peut stocker un maximum de 20 octets ; les valeurs de plus de 20 octets sont tronquées. Si cette valeur tronquée correspond aux valeurs tronquées suivantes, les accès suivants sont dédupliqués.

```js
s.purchaseID = "ABC123";
```

> [!NOTE] N’utilisez pas de fonction d’organisation aléatoire pour générer un ID d’achat. Adobe recommande d’utiliser une couche [de](../../prepare/data-layer.md) données pour stocker un ID d’achat donné.
