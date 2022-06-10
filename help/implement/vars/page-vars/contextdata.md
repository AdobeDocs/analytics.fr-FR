---
title: contextData
description: Les variables de données contextuelles vous permettent de définir des variables personnalisées sur chaque page que les règles de traitement peuvent lire.
feature: Variables
exl-id: f2c747a9-1a03-4f9f-8025-9f4745403a81
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 79%

---

# contextData

Les variables de données contextuelles vous permettent de définir des variables personnalisées sur chaque page que les règles de traitement peuvent lire. Au lieu d’affecter explicitement des valeurs aux variables Analytics dans votre code, vous pouvez envoyer des données dans des variables de données contextuelles. Les règles de traitement prennent ensuite les valeurs des variables de données contextuelles et les transfèrent dans les variables Analytics respectives. Voir [Règles de traitement](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) dans le guide d’utilisation destiné à l’administrateur.

Les variables de données contextuelles permettent aux équipes de développement de collecter des données dans des éléments nommés plutôt que dans des variables numérotées. Par exemple, au lieu de demander aux équipes de développement d’affecter l’auteur de la page à `eVar10`, vous pouvez demander à ce qu’elles l’affectent à `s.contextData["author"]` à la place. Un administrateur Analytics de votre entreprise peut alors créer des règles de traitement pour mapper des variables de données contextuelles dans des variables d’analyse pour la création de rapports. En fin de compte, les équipes de développement se soucient uniquement des variables de données contextuelles au lieu des nombreuses variables de page proposées par Adobe.

## Variables de données contextuelles utilisant le SDK Web

Si un champ XDM n’est pas [mappé pour Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html), il est automatiquement inclus en tant que variable de données contextuelles. Vous pouvez ensuite utiliser [Règles de traitement](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) pour affecter la variable de données contextuelles à la variable Analytics souhaitée.

Bien qu’il soit recommandé de mapper les données aux champs XDM corrects dans le flux de données, cette méthode obtient des résultats similaires.

## Variables de données contextuelles utilisant l’extension Adobe Analytics

La collecte de données Adobe Experience Platform ne dispose pas d’un emplacement dédié pour définir des variables de données contextuelles. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.contextData dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.contextData` ne prend pas directement une valeur. Définissez plutôt les propriétés de cette variable sur une chaîne.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* Les variables de données contextuelles valides contiennent uniquement des caractères alphanumériques, des traits de soulignement et des points. Adobe ne garantit pas la collecte de données dans les règles de traitement si vous incluez d’autres caractères, tels que des tirets.
* Ne commencez pas les variables de données contextuelles par `"a."`. Ce préfixe est réservé et utilisé par Adobe. Par exemple, n’utilisez pas `s.contextData["a.InstallEvent"]`.
* Les variables de données contextuelles ne sont pas sensibles à la casse. Les variables `s.contextData["example"]` et `s.contextData["EXAMPLE"]` sont identiques.

## Utiliser des règles de traitement pour renseigner les variables d’analyse

>[!WARNING]
>
>Les variables de données contextuelles sont ignorées après l’exécution des règles de traitement. Si aucune règle de traitement n’est active, ce qui place les valeurs dans des variables, ces données sont définitivement perdues !

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

## Incrémentation des événements à l’aide de variables de données contextuelles

Lors de la création de règles de traitement, vous pouvez affecter des variables de données contextuelles à des événements.

* Si une variable de données contextuelles contient n’importe quel type de texte, l’événement est incrémenté d’une unité.
* Si une variable de données contextuelles contient un entier, l’événement est incrémenté de ce nombre entier.

```js
// Assigning this context data variable to an event increments it by one
s.contextData["example_text"] = "Text value";

// Assigning this context data variable to an event increments it by four
s.contextData["example_number"] = "4";
```
