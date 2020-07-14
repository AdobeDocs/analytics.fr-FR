---
title: contextData
description: Les variables de données contextuelles vous permettent de définir des variables personnalisées sur chaque page que les règles de traitement peuvent lire.
translation-type: tm+mt
source-git-commit: 44ee19e468b9455c8c510421e507dd3f091fbc88
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 88%

---


# contextData

Les variables de données contextuelles vous permettent de définir des variables personnalisées sur chaque page que les règles de traitement peuvent lire. Au lieu d’affecter explicitement des valeurs aux variables Analytics dans votre code, vous pouvez envoyer des données dans des variables de données contextuelles. Les règles de traitement prennent ensuite les valeurs des variables de données contextuelles et les transfèrent dans les variables Analytics respectives. Voir [Règles de traitement](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) dans le guide d’utilisation Administrateur.

Les variables de données contextuelles permettent aux équipes de développement de collecter des données dans des éléments nommés plutôt que dans des variables numérotées. Par exemple, au lieu de demander aux équipes de développement d’affecter l’auteur de la page à `eVar10`, vous pouvez demander à ce qu’elles l’affectent à `s.contextData["author"]` à la place. Un administrateur Analytics de votre entreprise peut alors créer des règles de traitement pour mapper des variables de données contextuelles dans des variables d’analyse pour la création de rapports. En fin de compte, les équipes de développement se soucient uniquement des variables de données contextuelles au lieu des nombreuses variables de page proposées par Adobe.

## Variables de données contextuelles dans Adobe Experience Platform Launch

Launch ne dispose pas d’un emplacement dédié pour définir des variables de données contextuelles. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.contextData dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.contextData` ne prend pas directement une valeur. Définissez plutôt les propriétés de cette variable sur une chaîne.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* Les variables de données contextuelles valides contiennent uniquement des caractères alphanumériques, des traits de soulignement et des points. Adobe ne garantit pas la collecte de données dans les règles de traitement si vous incluez d’autres caractères, tels que des tirets.
* Ne commencez pas les variables de données contextuelles par `"a."`. Ce préfixe est réservé et utilisé par Adobe. Par exemple, n’utilisez pas `s.contextData["a.InstallEvent"]`.
* Les variables de données contextuelles ne sont pas sensibles à la casse. Les variables `s.contextData["example"]` et `s.contextData["EXAMPLE"]` sont identiques.

## Utiliser des règles de traitement pour renseigner les variables d’analyse

>[!IMPORTANT] Les variables de données contextuelles sont ignorées après l’exécution des règles de traitement. Si aucune règle de traitement n’est active, ce qui place les valeurs dans des variables, ces données sont définitivement perdues !

1. Mettez à jour votre mise en œuvre pour définir les noms et valeurs des variables de données contextuelles.
2. Connectez-vous à Adobe Analytics et accédez à Administrateur > Suites de rapports.
3. Sélectionnez la suite de rapports souhaitée, puis sélectionnez Modifier les paramètres > Général > Règles de traitement.
4. Créez une règle de traitement qui définit une variable Analytics sur la valeur de la variable de données contextuelles.
5. Enregistrez les modifications.

Les règles de traitement prennent immédiatement effet une fois enregistrées. Elles ne s’appliquent pas aux données historiques.

## Envoyer des données contextuelles dans un appel de suivi de lien

Incluez la variable de données contextuelles comme propriété de `contextData` dans [`s.linkTrackVars`](../config-vars/linktrackvars.md) :

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```

## Incrémenter des événements à l’aide de variables de données contextuelles

Lors de la création de règles de traitement, vous pouvez affecter des variables de données contextuelles à des événements.

* Si une variable de données contextuelles contient n’importe quel type de texte, le événement est incrémenté d’une unité.
* Si une variable de données contextuelles contient un entier, le événement est incrémenté de ce nombre entier.

```js
// Assigning this context data variable to an event increments it by one
s.contextData["example_text"] = "Text value";

// Assigning this context data variable to an event increments it by four
s.contextData["example_number"] = "4";
```
