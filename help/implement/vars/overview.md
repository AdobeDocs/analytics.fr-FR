---
title: Présentation des variables, fonctions, méthodes et plug-ins
description: Découvrez les variables que vous pouvez inclure dans les données que vous envoyez à Adobe pour améliorer la création de rapports.
keywords: appmeasurement,variables,vars,configuration,page,implementation
translation-type: tm+mt
source-git-commit: 7a1c3c7ed0e509969e281e865e8ff2c969a18bcb

---


# Présentation des variables, fonctions, méthodes et plug-ins

Adobe Analytics fournit plusieurs variables pour collecter des données d’analyse. Les variables de cette section sont divisées en plusieurs sections :

* **Les variables** de page sont des valeurs généralement utilisées directement dans les rapports. Les variables de page courantes sont `props`, `eVars`et `events`.
* **Les variables** de configuration sont des valeurs de paramètres qui permettent de s’assurer que les données correctes parviennent à Adobe. Les variables de configuration courantes sont `trackingServerSecure`, `charSet`et `linkTrackVars`. En règle générale, les variables de configuration ne renseignent pas les valeurs de dimension.
* **Les fonctions et méthodes** sont des éléments de code qui exécutent une tâche spécifique lorsqu’elles sont référencées. Les fonctions courantes sont `t()`, `tl()`et `clearVars()`.

## Variables et méthodes d’implémentation

Adobe propose plusieurs méthodes pour implémenter Adobe Analytics. Chaque page comporte une section sur la manière de mettre en oeuvre la variable à l’aide de Launch et AppMeasurement pour JavaScript.

## Ordre des opérations

Les bibliothèques AppMeasurement publiées par Adobe Analytics suivent un ordre spécifique lors de l’envoi de données à Adobe. Si vous exécutez ces tâches dans l’ordre, les données peuvent être incomplètes.

1. Si votre site utilise une couche de données, assurez-vous que toutes les variables applicables sont renseignées en premier. See [Data layer](../prepare/data-layer.md) for more information.
2. Utilisez la couche de données pour renseigner les variables Analytics. Si vous utilisez Lancer, cette tâche est facilement accomplie en utilisant des éléments de données, puis en affectant l’élément de données à une variable. Voir Eléments [de](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html) données dans le guide de l’utilisateur de lancement.
3. Appelez la fonction de suivi. La plupart des bibliothèques AppMeasurement utilisent la `t()` fonction, mais certains kits SDK mobiles l’utilisent `track()`. Lorsque la fonction de suivi est appelée, toutes les variables prises en charge définies dans l’objet Analytics sont envoyées à Adobe sous la forme d’une demande d’image.

## Caractères interdits

Les caractères et chaînes suivants ne sont jamais autorisés dans les variables JavaScript.

* Tabulation (`0x09`)
* Retour chariot (`0x0D`)
* Nouvelle ligne (`0x0A`)
* HTML tags (e.g. `<b></b>` or `&#153`)

Certaines variables ont des limitations ou des exigences de syntaxe supplémentaires. Par exemple, la `products` variable réserve des points-virgules et des virgules pour délimiter des produits et des catégories distincts.
