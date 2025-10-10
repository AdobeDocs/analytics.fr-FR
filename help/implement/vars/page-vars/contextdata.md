---
title: contextData
description: Les variables de données contextuelles vous permettent de définir des variables personnalisées sur chaque page que les règles de traitement peuvent lire.
feature: Appmeasurement Implementation
exl-id: f2c747a9-1a03-4f9f-8025-9f4745403a81
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 68%

---

# contextData

Les variables de données contextuelles vous permettent de définir des variables personnalisées sur chaque page que les règles de traitement peuvent lire. Au lieu d’affecter explicitement des valeurs aux variables Analytics dans votre code, vous pouvez envoyer des données dans des variables de données contextuelles. Les règles de traitement prennent ensuite les valeurs des variables de données contextuelles et les transfèrent dans les variables Analytics respectives. Voir [Règles de traitement](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) dans le guide d’utilisation destiné à l’administrateur.

Les variables de données contextuelles permettent aux équipes de développement de collecter des données dans des éléments nommés plutôt que dans des variables numérotées. Par exemple, au lieu de demander aux équipes de développement d’affecter l’auteur de la page à `eVar10`, vous pouvez demander à ce qu’elles l’affectent à `s.contextData["author"]` à la place. Un administrateur Analytics de votre entreprise peut alors créer des règles de traitement pour mapper des variables de données contextuelles dans des variables d’analyse pour la création de rapports. En fin de compte, les équipes de développement se préoccupent uniquement des variables de données contextuelles, plutôt que des nombreuses variables de page proposées par Adobe.

## Variables de données contextuelles utilisant le SDK Web

Si vous utilisez l’objet [**XDM**](/help/implement/aep-edge/xdm-var-mapping.md), tous les champs qui ne sont pas mappés à une variable Adobe Analytics sont automatiquement inclus en tant que variable de données contextuelles. Vous pouvez également définir explicitement des données contextuelles à l’aide de l’objet XDM. Vous pouvez ensuite utiliser [Règles de traitement](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) pour affecter la variable de données contextuelles à la variable Analytics souhaitée.  Voir [&#x200B; Mappage d’autres champs XDM aux variables Analytics &#x200B;](../../aep-edge/xdm-var-mapping.md#mapping-other-xdm-fields-to-analytics-variables) pour plus d’informations.

Si vous utilisez l’objet [**data**](/help/implement/aep-edge/data-var-mapping.md), toutes les variables de données contextuelles résident dans `data.__adobe.analytics.contextData` en tant que paires clé-valeur :

```js
alloy("sendEvent", {
  "data": {
    "__adobe": {
      "analytics": {
        "contextData": {
          "example_variable": "Example value",
          "second_example": "Another value"
        }
      }
    }
  }
});
```

L’interface [Règles de traitement](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) affiche les `example_variable` et les `second_example` dans les menus déroulants applicables.

## Variables de données contextuelles utilisant l’extension Adobe Analytics

La collecte de données Adobe Experience Platform ne dispose pas d’un emplacement dédié pour la définition des variables de données contextuelles. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.contextData dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.contextData` ne prend pas directement une valeur. Au lieu de cela, définissez les propriétés de cette variable sur une chaîne.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* Les variables de données contextuelles valides contiennent uniquement des caractères alphanumériques, des traits de soulignement et des points. Adobe ne garantit pas la collecte de données dans les règles de traitement si vous incluez d’autres caractères, tels que des tirets.
* Ne commencez pas les variables de données contextuelles par `"a."`. Ce préfixe est réservé et utilisé par Adobe. Par exemple, n’utilisez pas `s.contextData["a.InstallEvent"]`.
* Les variables de données contextuelles ne sont pas sensibles à la casse. Les variables `s.contextData["example"]` et `s.contextData["EXAMPLE"]` sont identiques.
* Une clé unique ne peut pas contenir plusieurs valeurs. Si vous souhaitez utiliser des variables de données contextuelles pour des variables à plusieurs valeurs, concaténez toutes les valeurs à l’aide d’un délimiteur (généralement une virgule) et transmettez-les dans une [prop de liste](prop.md#list-props) ou une [variable de liste](list.md) à l’aide de règles de traitement.

## Utiliser des règles de traitement pour renseigner les variables d’analyse

>[!WARNING]
>
>Les variables de données contextuelles sont ignorées après l’exécution des règles de traitement. Si aucune règle de traitement n’est active, ce qui place les valeurs dans des variables, ces données sont définitivement perdues !

1. Mettez à jour votre mise en œuvre pour définir les noms et valeurs des variables de données contextuelles.
2. Connectez-vous à Adobe Analytics et accédez à **[!UICONTROL Admin]** > **[!UICONTROL Report]** Suites.
3. Sélectionnez la suite de rapports souhaitée, puis accédez à **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Règles de traitement]**.
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
