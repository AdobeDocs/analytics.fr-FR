---
title: prop
description: Variables personnalisées que vous pouvez utiliser dans votre mise en œuvre.
feature: Appmeasurement Implementation
exl-id: 0d0ff8cd-1d8c-4263-866d-e51ad66148b0
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 85%

---

# prop

*Cette page d’aide décrit comment implémenter des props. Pour plus d’informations sur le fonctionnement des props en tant que dimension, consultez [prop](/help/components/dimensions/prop.md) dans le guide d’utilisation Composants.*

Les props sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Elles ne persistent pas au-delà de l’accès défini.

>[!TIP]
>
>Dans la plupart des cas, Adobe recommande d’utiliser des [eVars](evar.md). Dans les versions précédentes d’Adobe Analytics, les props et eVars présentaient des avantages et des inconvénients les uns pour les autres. Cependant, Adobe a amélioré les eVars à un point tel qu’elles remplissent désormais presque tous les cas d’utilisation des props.

Si vous disposez d’un [document de conception de solution](/help/implement/prepare/solution-design.md), vous pouvez attribuer ces dimensions personnalisées aux valeurs propres à votre entreprise. Le nombre de props disponibles dépend de votre contrat avec Adobe. Si le contrat que vous avez conclu avec Adobe le prévoit, vous pouvez obtenir jusqu’à 75 props.

## Props utilisant le SDK Web

Les props sont mappées aux variables suivantes :

* [Objet XDM](/help/implement/aep-edge/xdm-var-mapping.md) : `xdm._experience.analytics.customDimensions.props.prop1` - `xdm._experience.analytics.customDimensions.props.prop75` - les props de liste sont spécifiées dans un [ensemble distinct de champs](#list-props-web-sdk).
* [Objet de données](/help/implement/aep-edge/data-var-mapping.md) : `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` ; ou `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` - les props de liste sont incluses dans ces champs.

## Props utilisant l’extension Adobe Analytics

Vous pouvez définir des props lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics, et le [!UICONTROL Type d’action] sur [!UICONTROL Définir les variables].
6. Recherchez la section [!UICONTROL Props].

Vous pouvez définir une prop sur une valeur ou un élément de données. Vous pouvez également copier la valeur d’une autre variable Analytics.

## s.prop1 - s.prop75 dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Chaque variable prop est une chaîne qui contient des valeurs personnalisées propres à votre organisation. Leur longueur maximale est de 100 octets ; les valeurs de plus de 100 octets sont automatiquement tronquées lorsqu’elles sont envoyées à Adobe.

```js
s.prop1 = "Example custom value";
```

## Props de liste

Les props de liste désignent un paramètre appliqué aux props qui permet à la variable de contenir plusieurs valeurs dans le même accès. Si ce paramètre n’est pas activé ou si un délimiteur incorrect est utilisé, la variable est traitée comme une valeur unique.

### Configuration des props de liste

Activez les props de liste dans [Variables de trafic](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) sous les paramètres de la suite de rapports. Assurez-vous que le délimiteur souhaité est correctement configuré. Adobe ne fournit pas de délimiteur par défaut.

>[!TIP]
>
>Les délimiteurs courants utilisés dans les mises en œuvre sont une virgule (`,`), deux-points (`:`), un point-virgule (`;`) ou une barre verticale (`|`). Vous pouvez utiliser n’importe quel délimiteur ASCII non étendu qui correspond le mieux à votre mise en œuvre.

### Définir des props de liste à l’aide du SDK Web {#list-props-web-sdk}

Si vous utilisez l’objet [**XDM**](/help/implement/aep-edge/xdm-var-mapping.md), les props de liste sont mappées à `xdm._experience.analytics.customDimensions.listProps.prop1.values[]` - `xdm._experience.analytics.customDimensions.listProps.prop75.values[]`. Le SDK Web utilise automatiquement le délimiteur correct répertorié sous les paramètres de la suite de rapports. Si vous définissez le délimiteur dans le champ XDM (par exemple, `xdm._experience.analytics.customDimensions.props.prop1.delimiter`), cela remplace le délimiteur automatiquement récupéré à partir des paramètres de la suite de rapports et peut entraîner une analyse incorrecte de la chaîne de props de liste.

Si vous utilisez l’[**objet de données**](/help/implement/aep-edge/data-var-mapping.md), les props de liste utilisent les mêmes champs que les props standard et suivent la syntaxe d’AppMeasurement.

### Définir des props de liste à l’aide de l’extension Adobe Analytics et d’AppMeasurement

Une fois que vous avez configuré les props de liste dans les paramètres de la suite de rapports avec le délimiteur souhaité, il n’y a aucune différence de mise en œuvre autre que l’utilisation du délimiteur.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT]
>
>Les propriétés de liste sont toujours soumises à la longueur maximale de 100 octets. Les propriétés de liste sont plus faciles à atteindre et à tronquer, puisqu’elles peuvent contenir plusieurs valeurs. Utilisez des abréviations ou des valeurs de raccourcissement si vous pouvez atteindre cette limite de 100 octets.

Si vous définissez la même valeur plusieurs fois dans une prop de liste, elle est dédupliquée dans les rapports. Analysis Workspace comptabilise le nombre d’accès où une valeur est affichée et non le nombre d’occurrences d’une valeur dans les données.
