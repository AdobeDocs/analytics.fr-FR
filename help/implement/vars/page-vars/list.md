---
title: list
description: Variables personnalisées qui contiennent plusieurs valeurs dans le même accès.
translation-type: ht
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# list

Les variables de liste sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Elles fonctionnent de la même manière que les eVars, sauf qu’elles peuvent contenir plusieurs valeurs dans le même accès. Les variables de liste n’ont pas de limite de caractères.

Veillez à consigner dans votre [document de conception de solution](../../prepare/solution-design.md) la manière dont vous utilisez chaque variable de liste et sa logique.

> [!NOTE] Les variables de liste stockent les 250 valeurs les plus récentes par visiteur. S’il existe plus de 250 valeurs uniques pour un visiteur donné, les valeurs les plus anciennes ne sont pas attribuées aux mesures.

## Configuration de variables de liste dans les paramètres de la suite de rapports

Veillez à configurer chaque variable de liste dans les paramètres de la suite de rapports avant de l’utiliser dans votre mise en œuvre. Reportez-vous à la section [Variables de conversion](/help/admin/admin/conversion-var-admin/list-var-admin.md) dans le guide Administrateur.

## Variables de liste dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Launch pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.list1 - s.list3 dans AppMeasurement et l’éditeur de code personnalisé de Launch

Chaque variable de liste est une chaîne qui contient des valeurs personnalisées propres à votre organisation. Celles-ci n’ont pas de nombre maximal d’octets ; toutefois, chaque valeur individuelle ne peut pas dépasser 255 octets. Le délimiteur que vous utilisez est déterminé lors de la configuration de la variable dans les paramètres de la suite de rapports. N’utilisez pas d’espaces lorsque vous délimitez plusieurs éléments.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

> [!TIP] Si vous définissez des valeurs en double dans le même accès, Adobe déduplique toutes les instances de ces valeurs. Par exemple, si vous définissez `s.list1 = "Example,Example";`, une instance est comptabilisée dans les rapports.

## Comparer les props de liste et les variables de liste

Les props de liste et les variables de liste peuvent toutes deux contenir plusieurs valeurs dans le même accès. Cependant, il existe plusieurs différences clés entre ces deux types de variables.

* Toute prop peut devenir une prop de liste. Vous pouvez effectivement avoir jusqu’à 75 props de liste, si chaque prop est une prop de liste. Il n’y a que 3 variables de liste disponibles.
* Les props de liste sont limitées à 100 octets pour l’ensemble de la variable. Les variables de liste ont une limite de 255 octets par valeur et aucune limite totale d’octets.
* Les propriétés de liste ne persistent pas au-delà de l’accès qu’elles sont définies. Les variables de liste ont le paramètre d’expiration souhaité. Toutefois, avec le [traitement de l’heure des rapports](/help/components/vrs/vrs-report-time-processing.md), vous pouvez appliquer une attribution personnalisée aux props de liste et aux variables de liste.
