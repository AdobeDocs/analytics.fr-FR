---
title: events
description: Définissez la variable events, qui gouverne la plupart des mesures de votre site.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# events

Les dimensions et les mesures sont des composants essentiels des rapports. La `events` variable est responsable de la collecte de données de nombreuses mesures sur votre site.

## Evénements dans Adobe Experience Platform Launch

Vous pouvez définir des événements lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Règles] , puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le type [!UICONTROL d’] action sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Evénements] .

Plusieurs fonctionnalités sont disponibles :

* Une liste déroulante vous permet de sélectionner l’événement à inclure.
* Champ de texte facultatif pour la sérialisation. See [event serialization](event-serialization.md) for more information.
* Champ de texte facultatif pour une valeur d’événement. Vous pouvez inclure une devise pour les événements de devise ou un entier pour les événements non monétaires afin de les incrémenter plusieurs fois. Par exemple, la sélection `event1` sous la liste déroulante et `10` dans ce champ est incrémentée `event1` de 10 pour les rapports.
* Bouton permettant d’ajouter un autre événement. Il n’existe pas de limite raisonnable au nombre d’événements que vous pouvez inclure dans un accès.

## s.events dans AppMeasurement et Lancement de l’éditeur de code personnalisé

La `s.events` variable est une chaîne qui contient une liste d’événements délimités par des virgules à inclure dans l’accès. Il n’y a pas de limite d’octets pour cette variable. Elle n’est donc pas tronquée. Les valeurs valides sont les suivantes :

* `event1` - `event1000`: Evénements personnalisés, définissez la valeur souhaitée. Enregistrez la manière dont vous utilisez chaque événement dans le document [de conception de](../../../prepare/solution-design.md)solution de votre entreprise. Le nombre d’événements disponibles dépend du contrat Analytics de votre entreprise. La plupart des organisations utilisant des contrats non hérités disposent de 1 000 événements personnalisés. Contactez le gestionnaire de compte de votre entreprise si vous ne savez pas combien d’événements personnalisés vous sont accessibles.
* `purchase`: Incrémente la mesure Commandes de 1 et prend les valeurs définies dans la `products` variable pour calculer les unités et les recettes. Voir Evénement [d’](event-purchase.md) achat pour en savoir plus.
* `prodView`: Incrémente la mesure &quot;Consultations produits&quot;.
* `scOpen`: Incrémente la mesure Paniers.
* `scAdd`: Incrémente la mesure &quot;Ajouts au panier&quot;.
* `scRemove`: Incrémente la mesure &quot;Retraits du panier&quot;.
* `scView`: Incrémente la mesure &quot;Consultations du panier&quot;.
* `scCheckout`: Incrémente la mesure &quot;Passages en caisse&quot;.

> [!TIP] Cette variable est sensible à la casse. Evitez de mettre en majuscules les valeurs d’événement de manière à garantir la collecte exacte des données.

```js
// Set the events variable to a single value
s.events = "event1";

// Set the events variable to multiple values
s.events = "event1,event13,purchase";
```

### Incrémenter plusieurs fois les événements de compteur

Vous pouvez comptabiliser plusieurs événements personnalisés, le cas échéant. Attribuez un entier à l’événement souhaité dans la chaîne. Les événements créés dans les paramètres de la suite de rapports sont des événements de compteur par défaut.

```js
// Count event1 ten times
s.events = "event1=10";

// Count event1 twice and event2 once
s.events = "event1=2,event2";
```

> [!NOTE] Les événements de compteur ne prennent pas en charge les valeurs monétaires ou décimales. Utilisez des événements de devise pour la devise ou des événements numériques pour les valeurs décimales.

### Utiliser des événements de devise

Vous pouvez modifier un événement personnalisé pour utiliser une devise plutôt que des entiers. Les événements de devise sont automatiquement convertis en devise de la suite de rapports si la devise de la suite de rapports et la `currencyCode` variable ne correspondent pas. Elles sont utiles pour calculer les frais d&#39;expédition, les remises ou les remboursements. Vous pouvez définir des événements de devise dans la `products` variable si vous souhaitez attribuer l’événement à ce produit uniquement.

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

> [!NOTE] Si vous définissez une valeur monétaire dans la `events` variable et la `products` variable, la valeur monétaire dans `events` est utilisée. Evitez de définir des valeurs de devise dans les `events` variables et `products` les variables.

### Utiliser des événements numériques

Vous pouvez modifier un événement personnalisé en acceptant des valeurs décimales au lieu d’entiers. Les événements numériques se comportent de la même manière que les événements de devise, sauf qu’ils n’utilisent pas la conversion de devise. Vous pouvez définir des événements numériques dans la `products` variable si vous souhaitez attribuer l’événement à ce produit uniquement.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

> [!NOTE] Si vous définissez une valeur numérique dans la `events` variable et la `products` variable, la valeur numérique `events` est utilisée. Evitez de définir des valeurs numériques dans les `events` variables et `products` les variables.
