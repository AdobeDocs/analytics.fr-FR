---
title: events
description: Définissez la variable events, qui gouverne la plupart des mesures de votre site.
feature: Variables
exl-id: 6ef99ee5-40c3-4ff2-a75d-c97f2e8ec1f8
source-git-commit: 62f793491d2f95266a71bc217260353f8c040525
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 81%

---

# events

Les dimensions et les mesures sont des composants essentiels des rapports. La variable `events` est responsable de la collecte de données de nombreuses mesures sur votre site. Les événements incrémentent généralement les [mesures](/help/components/metrics/overview.md) dans les rapports.

Avant d’implémenter des événements, veillez à les créer et à les configurer sous [Événements de succès](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) dans les paramètres de la suite de rapports. Si vous prévoyez d’utiliser des événements personnalisés dans les accès de suivi de liens, assurez-vous que [`linkTrackVars`](../../config-vars/linktrackvars.md) et [`linkTrackEvents`](../../config-vars/linktrackevents.md) sont correctement configurés.

## Événements utilisant le SDK Web

Les événements personnalisés sont [mappé pour Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=fr) sous les champs XDM suivants :

* Les événements personnalisés 1 à 100 sont mappés sur `_experience.analytics.event1to100.event1` - `_experience.analytics.event1to100.event100`.
* Les événements personnalisés 101 à 200 sont mappés sur `_experience.analytics.event101to200.event100` - `_experience.analytics.event101to200.event200`.
* Ce modèle répète tous les 100 événements sur `_experience.analytics.event901to1000.event901` - `_experience.analytics.event901to1000.event1000`. `eventx.value` est utilisé pour spécifier le montant à incrémenter. `eventx.id` est utilisé pour [sérialisation](event-serialization.md).
* Les commandes sont associées à `commerce.purchases.value`.
* Les unités sont mappées à la somme de tous les `productListItems[].quantity` champs.
* Les recettes sont mises en correspondance avec la somme de toutes les `productListItems[].priceTotal` champs.
* Les vues de produits sont mappées sur `commerce.productListViews.value`.
* Les paniers sont associés à `commerce.productListOpens.value`.
* Les ajouts au panier sont mappés sur `commerce.productListAdds.value`.
* Les retraits du panier sont associés à `commerce.productListRemovals.value`.
* Les vues du panier sont mappées sur `commerce.productListViews.value`.
* Les passages en caisse sont mappés sur `commerce.checkouts.value`.

>[!NOTE]
>
>Si un événement est défini sous `productListItems` (par exemple, `productListItems._experience.analytics.event1.value`) et que cet événement ne figure pas encore dans ce champ, il est automatiquement ajouté à ce champ.

## Événements utilisant l’extension Adobe Analytics

Vous pouvez définir des événements lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Événements].

Plusieurs fonctionnalités sont disponibles :

* Une liste déroulante vous permet de sélectionner l’événement à inclure.
* Champ de texte facultatif pour la sérialisation. Voir [Sérialisation des événements](event-serialization.md) pour plus d’informations.
* Champ de texte facultatif pour une valeur d’événement. Vous pouvez inclure une devise pour les événements de devise ou un entier pour les événements non monétaires afin de les incrémenter plusieurs fois. Par exemple, sélectionner `event1` sous la liste déroulante et inclure `10` dans ce champ incrémente `event1` de 10 pour les rapports.
* Bouton permettant d’ajouter un autre événement. Vous pouvez ajouter autant d’événements que vous le souhaitez à une seule règle dans la raison.

## s.events dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.events` est une chaîne qui contient une liste d’événements délimités par des virgules à inclure dans l’accès. Il n’y a pas de limite d’octets pour cette variable. Elle n’est donc pas tronquée. Les valeurs valides sont les suivantes :

* `event1` - `event1000` : événements personnalisés, définissez la valeur souhaitée. Enregistrez la manière dont vous utilisez chaque événement dans le [document de conception de solution](../../../prepare/solution-design.md) de votre organisation. Le nombre d’événements disponibles dépend du contrat Analytics de votre organisation. La plupart des organisations utilisant des contrats non hérités disposent de 1 000 événements personnalisés. Contactez le gestionnaire de compte de votre organisation si vous ne savez pas combien d’événements personnalisés vous sont accessibles.
* `purchase` : incrémente la mesure [« Commandes »](/help/components/metrics/orders.md) de 1 et prend les valeurs définies dans la variable `products` pour calculer les [« Unités »](/help/components/metrics/units.md) et les [« Recettes »](/help/components/metrics/revenue.md). Voir [Événement d’achat](event-purchase.md) pour en savoir plus.
* `prodView` : incrémente la mesure [« Consultations de produit »](/help/components/metrics/product-views.md).
* `scOpen` : incrémente la mesure [« Paniers »](/help/components/metrics/carts.md).
* `scAdd` : incrémente la mesure [« Ajouts au panier »](/help/components/metrics/cart-additions.md).
* `scRemove` : incrémente la mesure [« Retraits du panier »](/help/components/metrics/cart-removals.md).
* `scView` : incrémente la mesure [« Consultations du panier »](/help/components/metrics/cart-views.md).
* `scCheckout` : incrémente la mesure [« Passages en caisse »](/help/components/metrics/checkouts.md).

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

Avant d’implémenter des événements de devise, veillez à configurer l’événement de votre choix sur « Devise » sous [Événements de succès](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) dans les paramètres de la suite de rapports.

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

Avant d’implémenter des événements numériques, veillez à configurer l’événement de votre choix sur « Numérique » sous [Événements de succès](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) dans les paramètres de la suite de rapports.

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
