---
title: events
description: Définissez la variable events, qui gouverne la plupart des mesures de votre site.
translation-type: tm+mt
source-git-commit: 2fd6e3b561d02bdbdd77b0be982614e765c870e2
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 80%

---


# events

Les dimensions et les mesures sont des composants essentiels des rapports. La variable `events` est responsable de la collecte de données de nombreuses mesures sur votre site. Les Événements incrémentent généralement [des mesures](/help/components/metrics/overview.md) dans les rapports.

Avant d’implémenter des événements, veillez à les créer et à les configurer sous événements [de](/help/admin/admin/c-success-events/success-event.md) réussite dans les paramètres de la suite de rapports. Si vous prévoyez d’utiliser des événements personnalisés dans les accès de suivi de liens, assurez-vous que [`linkTrackVars`](../../config-vars/linktrackvars.md) et [`linkTrackEvents`](../../config-vars/linktrackevents.md) sont correctement définis.

## Événements dans Adobe Experience Platform Launch

Vous pouvez définir des événements lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Événements].

Plusieurs fonctionnalités sont disponibles :

* Une liste déroulante vous permet de sélectionner l’événement à inclure.
* Champ de texte facultatif pour la sérialisation. Voir [Sérialisation des événements](event-serialization.md) pour plus d’informations.
* Champ de texte facultatif pour une valeur d’événement. Vous pouvez inclure une devise pour les événements de devise ou un entier pour les événements non monétaires afin de les incrémenter plusieurs fois. Par exemple, sélectionner `event1` sous la liste déroulante et inclure `10` dans ce champ incrémente `event1` de 10 pour les rapports.
* Bouton permettant d’ajouter un autre événement. Il n’existe pas de limite raisonnable au nombre d’événements que vous pouvez inclure dans un accès.

## s.events dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.events` est une chaîne qui contient une liste d’événements délimités par des virgules à inclure dans l’accès. Il n’y a pas de limite d’octets pour cette variable. Elle n’est donc pas tronquée. Les valeurs valides sont les suivantes :

* `event1` - `event1000` : événements personnalisés, définissez la valeur souhaitée. Enregistrez la manière dont vous utilisez chaque événement dans le [document de conception de solution](../../../prepare/solution-design.md) de votre organisation. Le nombre d’événements disponibles dépend du contrat Analytics de votre organisation. La plupart des organisations utilisant des contrats non hérités disposent de 1 000 événements personnalisés. Contactez le gestionnaire de compte de votre organisation si vous ne savez pas combien d’événements personnalisés vous sont accessibles.
* `purchase`: Incrémente la mesure [&quot;Commandes&quot;](/help/components/metrics/orders.md) de 1 et prend les valeurs définies dans la `products` variable pour calculer les [&quot;Unités&quot;](/help/components/metrics/units.md) et les [&quot;Recettes&quot;](/help/components/metrics/revenue.md). Voir [Événement d’achat](event-purchase.md) pour en savoir plus.
* `prodView`: Incrémente la mesure [&#39;Vues](/help/components/metrics/product-views.md) de produits.
* `scOpen`: Incrémente la mesure [&quot;Paniers&quot;](/help/components/metrics/carts.md) .
* `scAdd`: Incrémente la mesure [&quot;Ajouts au panier&quot;](/help/components/metrics/cart-additions.md) .
* `scRemove`: Incrémente la mesure [&quot;Retraits du panier&quot;](/help/components/metrics/cart-removals.md) .
* `scView`: Incrémente la [mesure](/help/components/metrics/cart-views.md) &#39;Vues de panier.
* `scCheckout`: Incrémente la mesure [&quot;Passages en caisse&quot;](/help/components/metrics/checkouts.md) .

>[!NOTE]
>
>Cette variable est sensible à la casse. Évitez de mettre en majuscules les valeurs d’événement de manière à garantir la collecte exacte des données.

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

>[!NOTE]
>
>Les événements de compteur ne prennent pas en charge les valeurs monétaires ou décimales. Utilisez des événements de devise pour la devise ou des événements numériques pour les valeurs décimales.

### Utiliser des événements de devise

Vous pouvez modifier un événement personnalisé pour utiliser une devise plutôt que des entiers. Les événements de devise sont automatiquement convertis en devise de la suite de rapports si la devise de la suite de rapports et la variable `currencyCode` ne correspondent pas. Elles sont utiles pour calculer les frais d’expédition, les remises ou les remboursements. Vous pouvez définir des événements de devise dans la variable `products` si vous souhaitez attribuer l’événement à ce produit uniquement.

Avant de mettre en oeuvre des événements de devises, veillez à définir le événement de votre choix sur &quot;Devise&quot; sous événements [de](/help/admin/admin/c-success-events/success-event.md) réussite dans les paramètres de la suite de rapports.

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in Report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in Report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

>[!NOTE]
>
>Si vous définissez une valeur monétaire dans la variable `events` et la variable `products`, la valeur monétaire dans `events` est utilisée. Évitez de définir des valeurs de devise dans les variables `events` et `products`.

### Utiliser des événements numériques

Vous pouvez modifier un événement personnalisé en acceptant des valeurs décimales au lieu d’entiers. Les événements numériques se comportent de la même manière que les événements de devise, sauf qu’ils n’utilisent pas la conversion de devise. Vous pouvez définir des événements numériques dans la variable `products` si vous souhaitez attribuer l’événement à ce produit uniquement.

Avant de mettre en oeuvre des événements numériques, veillez à définir le événement de votre choix sur &quot;Numérique&quot; sous événements [de](/help/admin/admin/c-success-events/success-event.md) réussite dans les paramètres de la suite de rapports.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

>[!NOTE]
>
>Si vous définissez une valeur numérique dans la variable `events` et la variable `products`, la valeur numérique `events` est utilisée. Évitez de définir des valeurs numériques dans les variables `events` et `products`.
