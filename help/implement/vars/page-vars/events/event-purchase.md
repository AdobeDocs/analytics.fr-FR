---
title: Evénement achat
description: Utilisez l’événement purchase pour collecter des données pour les mesures "Commandes", "Unités" et "Recettes".
translation-type: tm+mt
source-git-commit: 7a1c3c7ed0e509969e281e865e8ff2c969a18bcb

---


# Evénement achat

L’événement purchase est une valeur de la `events` variable. Cette valeur est utile pour les entreprises qui souhaitent collecter des données sur les recettes générées par leur site. Elle dépend fortement des `products` variables et `purchaseID` des variables.

Lorsque vous définissez un événement d’achat, il affecte les mesures suivantes :

* La mesure Commandes est incrémentée de 1
* La mesure &quot;Unités&quot; est incrémentée en fonction du nombre de produits dans la `products` variable
* La mesure Recettes augmente de la somme des paramètres de prix dans la `products` variable

## Définition de l’événement d’achat dans Adobe Experience Platform Launch

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Règles] , puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le type [!UICONTROL d’] action sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Evénements] et définissez la liste déroulante des événements sur [!UICONTROL purchase].

D’autres variables dépendantes, telles que `products` et `purchaseID` n’ont pas de champs dédiés dans Launch. Utilisez l’éditeur de code personnalisé suivant la syntaxe AppMeasurement pour ces variables.

## Définition de l’événement d’achat dans l’éditeur de code personnalisé AppMeasurement et Launch

L’événement purchase est une chaîne définie dans le cadre de la variable events.

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## Déduplication des événements d’achat

Lorsque vous déclenchez un événement d’achat, Adobe vérifie les éléments suivants :

* L’accès contient-il la `purchaseID` variable ? Dans le cas contraire, Adobe utilise les informations de l’accès pour créer un &quot;ID d’achat temporaire&quot;. Cet ID d’achat temporaire s’applique uniquement au visiteur de l’accès. Les 5 identifiants d’achat temporaires précédents sont stockés pour chaque identifiant visiteur par suite de rapports.
* L’ID d’achat temporaire correspond-il à l’un des cinq derniers ID d’achat temporaire stockés ? Si tel est le cas, la demande d’image est considérée comme un achat en double. Aucune variable de conversion, y compris l’événement d’achat, ne figure dans les rapports.
* Si la `purchaseID` variable est définie, correspond-elle à une valeur déjà collectée dans la suite de rapports pour tous les visiteurs ? Si tel est le cas, la demande d’image est considérée comme un achat en double. Aucune variable de conversion, y compris l’événement d’achat, ne figure dans les rapports.
