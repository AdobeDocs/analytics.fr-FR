---
title: purchaseID
description: Permet de dédupliquer les accès en fonction d’un identifiant d’achat unique.
feature: Appmeasurement Implementation
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 73%

---

# purchaseID

La variable `purchaseID` permet d’empêcher les accès contenant le même achat de gonfler les rapports. Par exemple, si un visiteur accède à votre page de confirmation d’achat, vous envoyez généralement des données sur les recettes générées par la transaction à Adobe. Si l’utilisateur actualise cette page plusieurs fois ou ajoute la page à ses signets pour la consulter ultérieurement, ces accès peuvent gonfler les rapports. La variable `purchaseID` déduplique les mesures lorsque plusieurs accès ont le même identifiant d’achat.

Lorsqu’Adobe reconnaît un accès comme un achat en double, toutes les données de conversion (telles que les eVars et les événements) ne s’affichent pas dans les rapports. Dans les flux de données, la colonne `duplicate_purchase` est définie sur `1`.

Les ID d’achat s’appliquent à tous les visiteurs et expirent après 37 mois. Si un visiteur définit un identifiant d’achat donné, puis un autre visiteur définit le même identifiant d’achat un an plus tard, le second achat est dédupliqué.

## ID d’achat à l’aide de Web SDK

L’ID d’achat est mappé aux variables suivantes :

* [Objet XDM](/help/implement/aep-edge/xdm-var-mapping.md) : `xdm.commerce.order.purchaseID`
* [Objet de données](/help/implement/aep-edge/data-var-mapping.md) : `data.__adobe.analytics.purchaseID`

## Identifiant d’achat utilisant l’extension Adobe Analytics

Vous pouvez définir l’identifiant d’achat lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics, et le [!UICONTROL Type d’action] sur [!UICONTROL Définir les variables].
6. Recherchez la section [!UICONTROL ID d’achat].

Vous pouvez définir l’ID d’achat sur une valeur ou un élément de données. Vous pouvez également copier la valeur d’une autre variable Analytics.

## s.purchaseID dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.purchaseID` est une chaîne qui contient un identifiant unique pour un achat. Celle-ci est définie sur le même accès qu’un événement d’achat. Utilisez uniquement des caractères alphanumériques pour renseigner cette variable.

Cette variable peut stocker un maximum de 20 octets ; les valeurs de plus de 20 octets sont tronquées. Si cette valeur tronquée correspond aux valeurs tronquées suivantes, les accès suivants sont dédupliqués.

```js
s.purchaseID = "ABC123";
```

Si vous utilisez la `digitalData` [couche de données](../../prepare/data-layer.md) :

```js
s.purchaseID = digitalData.transaction.transactionID;
```

>[!CAUTION]
>
>N’utilisez pas de fonction d’organisation aléatoire pour générer un identifiant d’achat.
