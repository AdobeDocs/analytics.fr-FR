---
title: Événement d’achat
description: Utilisez l’événement d’achat pour collecter des données pour les mesures Commandes, Unités et Recettes.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 92%

---


# Événement d’achat

L’événement d’achat est une valeur de la variable `events`. Cette valeur est utile pour les entreprises qui souhaitent collecter des données sur les recettes générées par leur site. Elle dépend fortement des variables [`products`](../products.md) et [`purchaseID`](../purchaseid.md).

Lorsque vous définissez un événement d’achat, celui-ci affecte les mesures suivantes :

* La mesure Commandes est incrémentée de 1
* La mesure Unités est incrémentée en fonction du nombre de produits dans la variable `products`
* La mesure Recettes augmente de la somme des paramètres de prix dans la variable `products`

>[!NOTE] Les recettes ne sont pas multipliées par le champ de quantité. For example, `s.products="Womens;Socks;5;4.50"` does not pass $22.50 into revenue; it passes $4.50. Make sure your implementation passes the total revenue for the quantity listed. Par exemple : `s.products="Womens;Socks;5;22.50"`.

## Définition de l’événement d’achat dans Adobe Experience Platform Launch

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Événements] et définissez la liste déroulante des événements sur [!UICONTROL achat].

D’autres variables dépendantes, telles que `products` et `purchaseID`, n’ont pas de champs dédiés dans Launch. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement pour ces variables.

## Définition de l’événement d’achat dans AppMeasurement et l’éditeur de code personnalisé de Launch

L’événement d’achat est une chaîne définie dans le cadre de la variable d’événements.

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## Déduplication des événements d’achat

Lorsque vous déclenchez un événement d’achat, Adobe vérifie les éléments suivants :

* L’accès contient-il la variable `purchaseID` ? Dans le cas contraire, Adobe utilise les informations de l’accès pour créer un « identifiant d’achat temporaire ». Cet identifiant d’achat temporaire s’applique uniquement au visiteur de l’accès. Les cinq identifiants d’achat temporaires précédents sont stockés pour chaque identifiant visiteur par suite de rapports.
* L’identifiant d’achat temporaire correspond-il à l’un des cinq derniers identifiants d’achat temporaire stockés ? Si tel est le cas, la demande d’image est considérée comme un achat en double. Aucune variable de conversion, y compris l’événement d’achat, ne figure dans les rapports.
* Si la variable `purchaseID` est définie, correspond-elle à une valeur déjà collectée dans la suite de rapports pour tous les visiteurs ? Si tel est le cas, la demande d’image est considérée comme un achat en double. Aucune variable de conversion, y compris l’événement d’achat, ne figure dans les rapports.
