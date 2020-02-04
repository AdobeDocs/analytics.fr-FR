---
title: eVar
description: Variables personnalisées que vous pouvez utiliser dans votre implémentation.
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# eVar

Les eVars sont des variables personnalisées que vous pouvez utiliser comme bon vous semble.

> [!TIP] Dans la plupart des cas, Adobe recommande d’utiliser des eVars plutôt que des props. Dans les versions précédentes d’Adobe Analytics, les props et eVars présentaient des avantages et des inconvénients les uns pour les autres. Toutefois, Adobe a amélioré les eVars afin qu’elles répondent à presque tous les cas d’utilisation des props.

Veillez à enregistrer la manière dont vous utilisez chaque eVar et sa logique dans le document [de conception de](../../prepare/solution-design.md)solution.

## Configuration des eVars dans les paramètres de la suite de rapports

Avant d’utiliser des eVars dans votre implémentation, veillez à configurer chaque eVar dans les paramètres de la suite de rapports. See [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin guide.

## eVars dans Adobe Experience Platform Launch

Vous pouvez définir des eVars lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Règles] , puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le type [!UICONTROL d’] action sur [!UICONTROL Définir des variables].
6. Localisez la section [!UICONTROL eVars] .

Vous pouvez sélectionner une eVar pour définir une valeur ou un élément de données. Vous pouvez également copier la valeur d’une autre variable Analytics.

## s.eVar1 - s.eVar250 dans AppMeasurement et lancement de l’éditeur de code personnalisé

Chaque eVar est une chaîne qui contient des valeurs personnalisées propres à votre entreprise. Leur longueur maximale est de 255 octets ; les valeurs de plus de 255 octets sont automatiquement tronquées lorsqu’elles sont envoyées à Adobe.

```js
s.eVar1 = "Example custom value";
```

## eVars de compteur

Les valeurs eVar contiennent généralement une valeur de chaîne. Vous pouvez toutefois configurer les eVars pour qu’elles contiennent un compteur. Par exemple, vous souhaitez comptabiliser le nombre de recherches internes effectuées avant un achat. Au lieu de définir une valeur de texte, utilisez la syntaxe suivante :

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

S’il y a plus de deux décimales, le compteur eVar arrondit la valeur à deux décimales. Un compteur eVar ne peut pas contenir de nombres négatifs.

## Avantages exclusifs pour les props ou eVars

Dans la version actuelle d’Adobe Analytics, les props et les eVars sont des variables personnalisées avec des fonctionnalités similaires. Cependant, elles présentent plusieurs différences majeures :

* Les données des props sont disponibles en quelques minutes dans les rapports. Les eVars peuvent prendre jusqu’à 30 minutes pour apparaître dans les rapports.
* Les props sont limitées à 100 octets dans les rapports. Les eVars sont limitées à 255 octets.
* Les props peuvent devenir des props de liste, qui acceptent plusieurs valeurs dans le même accès. Les variables de liste sont une variable distincte et seules trois variables de liste sont disponibles.
* Par défaut, les props ne persistent pas au-delà de l’accès défini. Les eVars ont une expiration personnalisée, ce qui vous permet de déterminer quand une eVar n’obtient plus le crédit d’un événement ultérieur. Si vous utilisez le traitement [du temps de](../../../components/vrs/vrs-report-time-processing.md)rapport, les props et les eVars peuvent utiliser n’importe quel modèle d’attribution que vous souhaitez.
