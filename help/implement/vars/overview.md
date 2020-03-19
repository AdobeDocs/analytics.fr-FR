---
title: Présentation des variables, fonctions, méthodes et plug-ins
description: Découvrez les variables que vous pouvez inclure dans les données que vous envoyez à Adobe pour améliorer les  de.
keywords: appmeasurement,variables,vars,configuration,page,implementation
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Présentation des variables, fonctions, méthodes et plug-ins

Adobe Analytics fournit plusieurs variables pour collecter des données d’analyse. Les variables de cette section sont divisées en plusieurs sections :

* **Les variables** de page sont des valeurs qui sont généralement utilisées directement dans les  de. Les variables de page courantes sont `props`, `eVars`et `events`.
* **Les variables** de configuration sont des valeurs de paramètres qui permettent de s’assurer que les données correctes parviennent à Adobe. Les variables de configuration courantes sont `trackingServerSecure`, `charSet`et `linkTrackVars`. En règle générale, les variables de configuration ne renseignent pas les valeurs de dimension.
* **Les fonctions et les méthodes** sont des éléments de code qui exécutent un  spécifique lorsqu’elles sont référencées. Les fonctions courantes sont `t()`, `tl()`et `clearVars()`.

## Variables et méthodes d’implémentation

Adobe   plusieurs méthodes pour implémenter Adobe Analytics. Chaque page  une section  sur la manière de mettre en oeuvre la variable à l’aide de Launch et AppMeasurement pour JavaScript.

## Ordre des opérations

Les bibliothèques AppMeasurement publiées par Adobe Analytics suivent un ordre spécifique lors de l’envoi de données à Adobe. Si vous exécutez ces  hors service, les données peuvent être incomplètes.

1. Si votre site utilise une couche de données, assurez-vous que toutes les variables applicables sont renseignées en premier. See [Data layer](../prepare/data-layer.md) for more information.
2. Utilisez la couche de données pour renseigner les variables Analytics. Si vous utilisez Lancer, ce  de est facile à réaliser en utilisant des éléments de données, puis en affectant l’élément de données à une variable. See [Data elements](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html) in the Launch user guide.
3. Appelez la fonction de suivi. La plupart des bibliothèques AppMeasurement utilisent la `t()` méthode, mais certains kits SDK mobiles l’utilisent `track()`. Lorsque la fonction de suivi est appelée, toutes les variables prises en charge définies dans l’objet Analytics sont envoyées à Adobe sous la forme d’une demande d’image.

## Caractères interdits

Les caractères et chaînes suivants ne sont jamais autorisés dans les variables JavaScript.

* Tabulation (`0x09`)
* Retour chariot (`0x0D`)
* Nouvelle ligne (`0x0A`)
* HTML tags (e.g. `<b></b>` or `&#153`)

Certaines variables ont des limitations ou des exigences de syntaxe supplémentaires. Par exemple, la `products` variable réserve des points-virgules et des virgules pour délimiter des produits et des  distincts.
