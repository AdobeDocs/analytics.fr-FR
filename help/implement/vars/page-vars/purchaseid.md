---
title: purchaseID
description: Permet de dédupliquer les accès en fonction d’un identifiant d’achat unique.
translation-type: ht
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# purchaseID

La variable `purchaseID` permet d’empêcher les accès contenant le même achat de gonfler les rapports. Par exemple, si un visiteur accède à votre page de confirmation d’achat, vous envoyez généralement des données sur les recettes générées par la transaction à Adobe. Si l’utilisateur actualise cette page plusieurs fois ou ajoute la page à ses signets pour la consulter ultérieurement, ces accès peuvent gonfler les rapports. La variable `purchaseID` déduplique les mesures lorsque plusieurs accès ont le même identifiant d’achat.

Lorsqu’Adobe reconnaît un accès comme un achat en double, toutes les données de conversion (telles que les eVars et les événements) ne s’affichent pas dans les rapports. Dans les flux de données, la colonne `duplicate_purchase` est définie sur `1`.

Les identifiants d’achat s’appliquent à tous les visiteurs et n’expirent pas. Si un visiteur définit un identifiant d’achat donné, puis un autre visiteur définit le même identifiant d’achat un an plus tard, le second achat est dédupliqué.

## Identifiant d’achat dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Launch pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.purchaseID dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.purchaseID` est une chaîne qui contient un identifiant unique pour un achat. Celle-ci est définie sur le même accès qu’un événement d’achat. Utilisez uniquement des caractères alphanumériques pour renseigner cette variable.

Cette variable peut stocker un maximum de 20 octets ; les valeurs de plus de 20 octets sont tronquées. Si cette valeur tronquée correspond aux valeurs tronquées suivantes, les accès suivants sont dédupliqués.

```js
s.purchaseID = "ABC123";
```

> [!NOTE] N’utilisez pas de fonction d’organisation aléatoire pour générer un identifiant d’achat. Adobe recommande d’utiliser une [couche de données](../../prepare/data-layer.md) pour stocker un identifiant d’achat donné.
