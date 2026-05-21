---
title: Résolution des problèmes de mise en œuvre de JavaScript
description: Découvrez les problèmes courants et les bonnes pratiques pour résoudre les problèmes de votre mise en œuvre JavaScript.
feature: Implementation Basics
exl-id: e7181e78-65bf-446d-8d5c-b47323dbec1d
role: Developer
TQID: https://experienceleague.adobe.com/U97L94cxnWYpnqsJ3FJh7EBbdIHpFHxfJP7uqoqrGgU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: c8add8f2-4250-4fd9-9cde-9707036c567did: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 702
ht-degree: 94%

---

# Résolution des problèmes de mise en œuvre de JavaScript

Vous trouverez ci-dessous plusieurs raisons pour lesquelles votre organisation peut rencontrer des problèmes lors de l’importation correcte des données dans Adobe Analytics.

## Utilisation de guillemets

La plupart des variables envoyées à Adobe sont des chaînes. Dans JavaScript, vous pouvez utiliser des guillemets simples ou doubles.

### Mixage de guillemets pour définir une variable

Il est recommandé de s&#39;assurer que vous êtes cohérent avec les types de devis utilisés. Si un guillemet simple désigne le début d’une chaîne, un guillemet simple doit être utilisé pour la fermer.

Par exemple, les deux `s.eVar1 = 'Value'` et `s.eVar1 = "Value"` sont valides. `s.eVar1 = 'Value"` n’est pas valide.

### Inclusion de guillemets simples ou doubles dans une chaîne

Il est parfois souhaitable d’inclure un guillemet simple ou double dans une chaîne. Par exemple, vous souhaitez inclure la valeur `Alex's sale` ou `John the "Hunter"` dans les rapports. Il existe deux méthodes pour inclure ces valeurs :

* **Utilisez l’autre type de guillemet** : par exemple, `s.eVar1 = "Alex's sale"` et `s.eVar1 = 'John the "Hunter"'` sont tous deux valides.
* **Échapper les guillemets** : utilisez une barre oblique inverse pour échapper les guillemets. Par exemple, `s.eVar1 = 'Alex\'s sale'` et `s.eVar1 = "John the \"Hunter\""` sont tous deux valides.

### Évitez d’utiliser des guillemets courbes.

Certains programmes convertissent automatiquement les guillemets neutres (`"..."` et `'...'`) en guillemets courbes (`"..."` et `'...'`). Évitez d’utiliser des éditeurs de documents (tels que Microsoft Word) ou de transmettre des fragments de code par courrier électronique. Les guillemets courbes ne peuvent pas être utilisés dans JavaScript.

## Référence à l’objet Analytics

Toutes les variables envoyées à Adobe utilisent l’objet Analytics. La plupart des mises en œuvre utilisent l’objet `s`. Veillez à inclure l’objet Analytics dans votre référence lorsque vous référencez des variables.

Par exemple, `s.eVar1 = 'Value'` est valide, alors que `eVar1 = 'Value'` ne l’est pas.

## Définir chaque variable une fois

Lorsqu’une fonction de suivi (`s.t()`) s’exécute, AppMeasurement prend toutes les variables définies et les compile dans une demande d’image. Si vous définissez une variable plusieurs fois dans votre mise en œuvre, seule la dernière valeur est utilisée. Assurez-vous que toutes les valeurs de variable contiennent la valeur correcte lors de l’exécution de la fonction de suivi.

## Correction de la casse des variables

Certaines variables utilisent des lettres majuscules. Les variables JavaScript sont sensibles à la casse. Veillez à utiliser la casse correcte lors de la définition de variables. Par exemple, `s.eVar1 = 'Value'` est valide, alors que `s.evar1 = 'Value'` ne l’est pas.

## Plug-ins

Certaines organisations utilisent des plug-ins pour améliorer leur mise en œuvre d’Adobe Analytics. Lors de la mise à niveau des versions d’AppMeasurement, n’oubliez pas de réinclure les plug-ins installés. Le code créé dans le [!UICONTROL Gestionnaire de code] ne comporte aucun code de plug-in. Effectuez une copie du code existant au cas où vous auriez besoin de revenir à une version précédente d’AppMeasurement.

## Espaces dans les valeurs de variable

Dans le langage HTML, plusieurs caractères créent un espace. Il s’agit notamment d’un espace, d’une tabulation et d’un retour chariot (ou nouvelle ligne). Examinez l’exemple suivant :

```html
<head>
  <title>
    Home Page
  </title>
</head>
<body>
<script language="javascript">
  s.pageName = document.title;
</script>
</body>
```

Dans ce cas, `document.title` renseigne `s.pageName`, qui reçoit la valeur de « page d’accueil ». Cependant, certains navigateurs peuvent interpréter l’espace blanc différemment. Le résultat peut être l’un des deux exemples suivants :

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

Ces deux valeurs de variable sont considérées comme distinctes dans Adobe Analytics. Toutefois, l’espace blanc est automatiquement supprimé à des fins d’affichage. Le résultat est un rapport qui affiche deux éléments de ligne « page d’accueil » apparemment identiques. Assurez-vous que les valeurs de variable ne contiennent pas d’espace blanc avant ou après la valeur souhaitée.

## Demandes d’image tronquées

Les implémentations qui renseignent de nombreuses variables avec des valeurs longues rencontrent parfois des demandes d’image tronquées. Certains navigateurs plus anciens, comme Internet Explorer, imposent une limite de 2 083 caractères aux URL de demande d’image. Si votre entreprise fait face à de très longues demandes d’image, essayez les méthodes suivantes :

* **Utilisez le service Experience Cloud ID** : les bibliothèques AppMeasurement 1.4.1 et ultérieures envoient automatiquement des demandes d’image POST HTTP lorsqu’elles sont trop longues. Les données envoyées à l’aide de cette méthode ne sont pas tronquées, quelle que soit leur longueur. Pour plus d’informations, consultez le [service Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr).
* **Utilisez des règles de traitement** : les [règles de traitement](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) peuvent copier des valeurs d’une variable vers une autre. Cette méthode vous évite de définir la même valeur dans plusieurs variables. Par exemple :

  Toujours exécuter :<br>
Remplacer la valeur de prop1 avec eVar1<br>
Remplacer la valeur d’eVar2 par eVar1<br>
Remplacer la valeur de prop2 avec eVar1<br>

  Définissez ensuite eVar1 dans votre implémentation :

  ```js
  s.eVar1 = "The quick brown fox jumps over the lazy dog";
  ```

* **Utilisez des variables dynamiques** : si votre implémentation renseigne de nombreuses variables avec la même valeur, vous pouvez utiliser des [variables dynamiques](/help/implement/vars/page-vars/dynamic-variables.md) pour raccourcir l’URL de la demande :

  ```js
  s.eVar1 = "The quick brown fox jumps over the lazy dog";
  s.eVar2 = "D=v1";
  s.prop1 = "D=v1";
  s.prop2 = "D=v1";
  ```

* **Utilisez des classifications** : si les noms de produit ou de page sont exceptionnellement longs, vous pouvez utiliser une valeur ou un code d’identification, puis utiliser les [classifications](/help/components/classifications/classifications-overview.md) pour afficher un nom plus convivial.
