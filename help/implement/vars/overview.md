---
title: Présentation des variables, fonctions, méthodes et plug-ins
description: Découvrez les variables que vous pouvez inclure dans les données que vous envoyez à Adobe pour améliorer la création de rapports.
keywords: appmeasurement,variables,vars,configuration,page,implémentation
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 98%

---


# Présentation des variables, fonctions, méthodes et plug-ins

Adobe Analytics fournit plusieurs variables pour collecter des données d’analyse. Les variables de cette section sont divisées en plusieurs sections :

* **Les variables de page** sont des valeurs généralement utilisées directement dans les rapports. Les variables de page courantes sont `props`, `eVars` et `events`.
* **Les variables de configuration** sont des valeurs de paramètres qui permettent de s’assurer que les données correctes parviennent à Adobe. Les variables de configuration courantes sont `trackingServerSecure`, `charSet` et `linkTrackVars`. En règle générale, les variables de configuration ne renseignent pas les éléments de dimension.
* **Les fonctions et méthodes** sont des éléments de code qui exécutent une tâche spécifique lorsqu’elles sont référencées. Les fonctions courantes sont `t()`, `tl()` et `clearVars()`.

## Variables et méthodes de mise en œuvre

Adobe propose plusieurs façons de mettre en œuvre Adobe Analytics. Chaque page comporte une section sur la manière de mettre en œuvre la variable à l’aide de Launch et AppMeasurement pour JavaScript.

## Ordre des opérations

Les bibliothèques AppMeasurement publiées par Adobe Analytics suivent un ordre spécifique lors de l’envoi de données à Adobe. Si vous exécutez ces tâches dans l’ordre, les données peuvent être incomplètes.

1. Si votre site utilise une couche de données, assurez-vous que toutes les variables applicables sont renseignées en premier. Pour plus d’informations, reportez-vous à la section [Couches de données](../prepare/data-layer.md).
2. Utilisez la couche de données pour renseigner les variables Analytics. Si vous utilisez Launch, cette tâche est facilement accomplie en utilisant des éléments de données, puis en affectant l’élément de données à une variable. Voir [Éléments de données](https://docs.adobe.com/content/help/fr-FR/launch/using/reference/manage-resources/data-elements..html) dans le guide d’utilisation de Launch.
3. Appelez la fonction de suivi. La plupart des bibliothèques AppMeasurement utilisent la méthode `t()`, mais certains kits SDK mobiles utilisent `track()`. Lorsque la fonction de suivi est appelée, toutes les variables prises en charge définies dans l’objet Analytics sont envoyées à Adobe sous la forme d’une demande d’image.

## Caractères interdits

Les caractères et chaînes suivants ne sont jamais autorisés dans les variables JavaScript.

* Tabulation (`0x09`)
* Retour chariot (`0x0D`)
* Nouvelle ligne (`0x0A`)
* Balises HTML (`<b></b>` ou `&#153`, par exemple)

Certaines variables ont des limitations ou des exigences de syntaxe supplémentaires. Par exemple, la variable [`products`](page-vars/products.md) réserve des points-virgules et des virgules pour délimiter des produits et des catégories distincts.
