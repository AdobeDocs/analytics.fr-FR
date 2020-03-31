---
title: eVar
description: Variables personnalisées que vous pouvez utiliser dans votre mise en œuvre.
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# eVar

*Cette page d’aide décrit la mise en oeuvre des eVars. Pour plus d’informations sur le fonctionnement des eVars en tant que dimension, voir[eVars](../../../components/c-variables/dimensionslist/reports-conversion.md)dans le guide de l’utilisateur Composants.*

Les eVars sont des variables personnalisées que vous pouvez utiliser comme bon vous semble.

> [!TIP] Dans la plupart des cas, Adobe recommande d’utiliser des eVars plutôt que des props. Dans les versions précédentes d’Adobe Analytics, les props et eVars présentaient des avantages et des inconvénients les uns pour les autres. Toutefois, Adobe a amélioré les eVars afin qu’elles répondent à presque tous les cas d’utilisation des props.

Veillez à enregistrer la manière dont vous utilisez chaque eVar et sa logique dans le [document de conception de solution](../../prepare/solution-design.md).

## Configurer des eVars dans les paramètres de la suite de rapports

Avant d’utiliser des eVars dans votre mise en œuvre, veillez à configurer chaque eVar dans les paramètres de la suite de rapports. Reportez-vous à la section [Variables de conversion](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) dans le guide Administrateur.

## eVars dans Adobe Experience Platform Launch

Vous pouvez définir des eVars lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Sous [!UICONTROL Actions], cliquez sur une [!UICONTROL Adobe Analytics - Set Variables] action existante ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la [!UICONTROL Extension] liste déroulante sur Adobe Analytics et la [!UICONTROL Action Type] sur [!UICONTROL Set Variables].
6. Locate the [!UICONTROL eVars] section.

Vous pouvez sélectionner une eVar pour définir une valeur ou un élément de données. Vous pouvez également copier la valeur d’une autre variable Analytics.

## s.eVar1 - s.eVar250 dans AppMeasurement et l’éditeur de code personnalisé de Launch

Chaque eVar est une chaîne qui contient des valeurs personnalisées propres à votre organisation. Leur longueur maximale est de 255 octets ; les valeurs de plus de 255 octets sont automatiquement tronquées lorsqu’elles sont envoyées à Adobe.

```js
s.eVar1 = "Example custom value";
```

## eVars de compteur

Les valeurs eVar contiennent généralement une valeur de chaîne. Vous pouvez toutefois configurer les eVars pour qu’elles contiennent un compteur. Par exemple, vous souhaitez comptabiliser le nombre de recherches internes effectuées avant un achat. Au lieu de définir une valeur de texte, utilisez la syntaxe suivante :

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

S’il y a plus de deux décimales, le compteur eVar arrondit la valeur à deux décimales. Un compteur eVar ne peut pas contenir de nombres négatifs.

> [!IMPORTANT] Vous devez d’abord configurer les eVars sur Compteur dans la Console d’administration avant d’utiliser les eVars de compteur. Reportez-vous à la section [Variables de conversion](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) dans le guide Administrateur.

## Avantages exclusifs aux props et aux eVars

Dans la version actuelle d’Adobe Analytics, les props et les eVars sont des variables personnalisées avec des fonctionnalités similaires. Cependant, elles présentent plusieurs différences majeures :

* Les données des props sont disponibles en quelques minutes dans les rapports. Il peut falloir jusqu’à 30 minutes avant que les eVars n’apparaissent dans les rapports.
* Les props sont limitées à 100 octets dans les rapports. Les eVars sont limitées à 255 octets.
* Les props peuvent devenir des props de liste, qui acceptent plusieurs valeurs dans le même accès. Les variables de liste sont une variable distincte et seules trois variables de liste sont disponibles.
* Par défaut, les props ne persistent pas au-delà de l’accès défini. Les eVars ont une expiration personnalisée, ce qui vous permet de déterminer quand une eVar n’obtient plus le crédit d’un événement ultérieur. Cependant, si vous utilisez le traitement [du temps de](../../../components/vrs/vrs-report-time-processing.md)rapport, les props et les eVars peuvent utiliser un modèle d’attribution personnalisé.
