---
title: contextData
description: Les variables de données contextuelles vous permettent de définir des variables personnalisées sur chaque page que les règles de traitement peuvent lire.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# contextData

Les variables de données contextuelles vous permettent de définir des variables personnalisées sur chaque page que les règles de traitement peuvent lire. Au lieu d’affecter explicitement des valeurs aux variables Analytics dans votre code, vous pouvez envoyer des données dans des variables de données contextuelles. Les règles de traitement prennent ensuite les valeurs des variables de données contextuelles et les transmettent dans les variables Analytics respectives. Voir [Règles de traitement](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) dans le guide d’utilisation destiné à l’administrateur.

Les variables de données contextuelles permettent aux équipes de développement de collecter des données dans des éléments nommés plutôt que dans des variables numérotées. Par exemple, au lieu de demander aux équipes de développement d’affecter l’auteur de la page `eVar10`, vous pouvez demander à ce qu’elles l’affectent `s.contextData["author"]` à la place. Un administrateur Analytics de votre entreprise peut alors créer des règles de traitement pour mapper des variables de données contextuelles dans des variables d’analyse pour les  de. Les équipes de développement ne s’inquiètent en fin de compte que des variables de données contextuelles au lieu des nombreuses variables de page  Adobe .

## Variables de données contextuelles dans Adobe Experience Platform Launch

Launch ne dispose pas d’un emplacement dédié pour définir des variables de données contextuelles. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.contextData dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.contextData` variable ne prend pas directement une valeur. Définissez plutôt les propriétés de cette variable sur une chaîne.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* Les variables de données contextuelles valides ne contiennent que des caractères alphanumériques, des traits de soulignement et des points. Adobe ne garantit pas la collecte de données dans les règles de traitement si vous incluez d’autres caractères, tels que des tirets.
* Ne  pas les variables de données contextuelles avec `"a."`. Ce préfixe est réservé et utilisé par Adobe. Par exemple, n’utilisez pas `s.contextData["a.InstallEvent"]`.
* Les variables de données contextuelles ne sont pas sensibles à la casse. Les variables `s.contextData["example"]` et `s.contextData["EXAMPLE"]` sont identiques.

## Utilisation de règles de traitement pour renseigner les variables d’analyse

> [!IMPORTANT] Les variables de données contextuelles sont ignorées après l’exécution des règles de traitement. Si aucune règle de traitement n’est active, ce qui place les valeurs dans des variables, ces données sont définitivement perdues !

1. Mettez à jour votre implémentation pour définir les noms et valeurs des variables de données contextuelles.
2. Connectez-vous à Adobe Analytics et accédez à Admin > Report Suites.
3. Sélectionnez une suite de rapports, puis cliquez sur Modifier les paramètres > Général > Règles de traitement.
4. Créez une règle de traitement qui définit une variable Analytics sur la valeur de la variable de données contextuelles.
5. Enregistrez les modifications.

Les règles de traitement prennent immédiatement effet une fois enregistrées. Elles ne s’appliquent pas aux données historiques.

## Envoyer des données contextuelles dans un appel de suivi de lien

Incluez la variable de données contextuelles comme propriété de `contextData` dans [`s.linkTrackVars`](../config-vars/linktrackvars.md):

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```
