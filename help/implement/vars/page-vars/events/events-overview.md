---
title: events
description: Définissez la variable  du, qui régit la plupart des mesures de votre site.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# events

Les dimensions et les mesures sont des composants essentiels des rapports. La `events` variable est responsable de la collecte de données de nombreuses mesures sur votre site.

##  dans Adobe Experience Platform Launch

Vous pouvez définir des  lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Rules] onglet, puis cliquez sur la règle souhaitée (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une [!UICONTROL Adobe Analytics - Set Variables] action existante ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la [!UICONTROL Extension] liste déroulante sur Adobe Analytics et la [!UICONTROL Action Type] sur [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Events] section.

Plusieurs fonctionnalités sont disponibles :

* Une liste déroulante vous permet de sélectionner le  à inclure
* Champ de texte facultatif pour la sérialisation. See [event serialization](event-serialization.md) for more information.
* Champ de texte facultatif pour une valeur de . Vous pouvez inclure une devise pour les  de devise ou un entier pour les  non monétaires pour les incrémenter plusieurs fois. Par exemple, la sélection `event1` sous la liste déroulante et `10` dans ce champ est incrémentée `event1` de 10 dans le .
* Bouton permettant d’ajouter un autre  de. Il n’existe pas de limite raisonnable au nombre de que vous pouvez inclure dans un accès.

## s.dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.events` variable est une chaîne qui contient un de délimité par des virgules à inclure dans l’accès. Il n’y a pas de limite d’octets pour cette variable. Elle n’est donc pas tronquée. Les valeurs valides sont les suivantes :

* `event1` - `event1000`:  personnalisé, définissez la valeur souhaitée. Enregistrez la manière dont vous utilisez chaque dans lede conception de [solution de votre entreprise](../../../prepare/solution-design.md). Le nombre de  de disponibles dépend du contrat Analytics de votre entreprise. La plupart des entreprises qui utilisent des contrats non hérités disposent de 1 000  personnalisées. Contactez le gestionnaire de compte de votre entreprise si vous ne savez pas combien de  personnalisées vous sont accessibles.
* `purchase`: Incrémente la mesure Commandes de 1 et prend les valeurs définies dans la `products` variable pour calculer les unités et les recettes. Pour plus d’informations, reportez-vous à la page [d’achat](event-purchase.md) du.
* `prodView`: Incrémente la mesure &quot; du produit&quot;.
* `scOpen`: Incrémente la mesure Paniers.
* `scAdd`: Incrémente la mesure &quot;Ajouts au panier&quot;.
* `scRemove`: Incrémente la mesure &quot;Retraits du panier&quot;.
* `scView`: Incrémente la mesure &quot; panier&quot;.
* `scCheckout`: Incrémente la mesure &quot;Passages en caisse&quot;.

> [!NOTE] Cette variable est sensible à la casse. Evitez de mettre en minuscules les valeurs de  pour garantir une collecte de données précise.

```js
// Set the events variable to a single value
s.events = "event1";

// Set the events variable to multiple values
s.events = "event1,event13,purchase";
```

### Incrémenter le de compteur  plusieurs fois

Vous pouvez comptabiliser les personnalisés plusieurs fois, le cas échéant. Attribuez un entier au  de votre choix dans la chaîne. Les  créées dans les paramètres de la suite de rapports sont par défaut des de compteur .

```js
// Count event1 ten times
s.events = "event1=10";

// Count event1 twice and event2 once
s.events = "event1=2,event2";
```

> [!NOTE] Les  de compteur ne prennent pas en charge les valeurs monétaires ou décimales. Utilisez les  de devise pour la devise ou les  numériques pour les valeurs décimales.

### Utiliser le de devises 

Vous pouvez modifier un personnalisé pour utiliser une devise plutôt que des entiers. Le de devise est automatiquement converti en devise de la suite de rapports si la devise de la suite de rapports et la `currencyCode` variable ne correspondent pas. Elles sont utiles pour calculer les frais d&#39;expédition, les remises ou les remboursements. Vous pouvez définir des  de devise dans la `products` variable si vous souhaitez attribuer le  uniquement à ce produit.

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

> [!NOTE] Si vous définissez une valeur de devise dans la `events` variable et la `products` variable, la valeur de devise dans `events` est utilisée. Evitez de définir des valeurs de devise dans les `events` variables et les `products` variables.

### Utiliser des  numériques

Vous pouvez modifier un personnalisé  accepter des valeurs décimales plutôt que des entiers. Les numériques se comportent de la même manière que les  de devise, sauf qu’ils n’utilisent pas la conversion de devise. Vous pouvez définir des  de numériques dans la `products` variable si vous souhaitez attribuer le  à ce produit uniquement.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

> [!NOTE] Si vous définissez une valeur numérique dans la `events` variable et la `products` variable, la valeur numérique `events` est utilisée. Evitez de définir des valeurs numériques dans les `events` variables et `products` les variables.
