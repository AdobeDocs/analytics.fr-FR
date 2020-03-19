---
title: prop
description: Variables personnalisées que vous pouvez utiliser dans votre implémentation.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# prop

Les props sont des variables personnalisées que vous pouvez utiliser comme bon vous semble.

> [!TIP] Dans la plupart des cas, Adobe recommande d’utiliser des eVars. Dans les versions précédentes d’Adobe Analytics, les props et eVars présentaient des avantages et des inconvénients les uns pour les autres. Toutefois, Adobe a amélioré les eVars afin qu’elles répondent à presque tous les cas d’utilisation des props. Voir [eVars](evar.md) pour une comparaison des fonctionnalités entre ces deux types de variables personnalisées.

Si votre entreprise utilise des props, veillez à enregistrer leur utilisation et leur logique dans votre [de conception](../../prepare/solution-design.md)de solution.

## Props dans Adobe Experience Platform Launch

Vous pouvez définir des props lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Rules] onglet, puis cliquez sur la règle souhaitée (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une [!UICONTROL Adobe Analytics - Set Variables] action existante ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la [!UICONTROL Extension] liste déroulante sur Adobe Analytics et la [!UICONTROL Action Type] sur [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Props] section.

Vous pouvez sélectionner une prop pour définir une valeur ou un élément de données. Vous pouvez également copier la valeur d’une autre variable Analytics.

## s.prop1 - s.prop75 dans AppMeasurement et lancement de l’éditeur de code personnalisé

Chaque variable prop est une chaîne qui contient des valeurs personnalisées propres à votre entreprise. Leur longueur maximale est de 100 octets ; les valeurs de plus de 100 octets sont automatiquement tronquées lorsqu’elles sont envoyées à Adobe.

```js
s.prop1 = "Example custom value";
```

## props de 

Les props  sont un paramètre appliqué aux props qui permet à la variable de contenir plusieurs valeurs dans le même accès. Si ce paramètre n’est pas activé ou si un délimiteur incorrect est utilisé, la variable est traitée comme une valeur unique.

### Configuration des props de 

Activez les props  dans les paramètres de la suite de rapports. See [Traffic variables](/help/admin/admin/c-traffic-variables/traffic-var.md) in the Admin user guide. Assurez-vous que le délimiteur souhaité est correctement configuré. Adobe ne fournit pas de délimiteur par défaut.

> [!TIP] Les délimiteurs courants utilisés dans les implémentations sont une virgule (`,`), deux-points (`:`), un point-virgule (`;`) ou une barre verticale (`|`). Vous pouvez utiliser n’importe quel délimiteur qui correspond le mieux à votre implémentation.

### Définition des props de 

Une fois que vous avez configuré les props  dans les paramètres de la suite de rapports avec le délimiteur souhaité, il n’y a aucune différence d’implémentation autre que l’utilisation du délimiteur.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

> [!IMPORTANT] Les props  sont toujours soumises à la longueur maximale de 100 octets. Les props de  sont plus faciles à atteindre et à tronquer, puisqu’elles peuvent contenir plusieurs valeurs. Utilisez des abréviations ou des valeurs de raccourcissement si vous pouvez atteindre cette limite de 100 octets.

Si vous définissez la même valeur plusieurs fois dans une prop de , elle est dédupliquée dans les  de.  Espace de travail  compte le nombre d’accès où une valeur est affichée et non le nombre d’occurrences d’une valeur dans les données.
