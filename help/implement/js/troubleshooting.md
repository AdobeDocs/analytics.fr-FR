---
title: Résolution des problèmes d’implémentation de JavaScript
description: Découvrez les problèmes courants et les bonnes pratiques pour résoudre les problèmes de votre implémentation JavaScript.
translation-type: tm+mt
source-git-commit: 8aa6932dcbb6dad88c27ba1cd4f5aad3bafcfc52

---


# Résolution des problèmes d’implémentation de JavaScript

Vous trouverez ci-dessous plusieurs raisons pour lesquelles votre entreprise peut rencontrer des problèmes lors de l’importation correcte des données dans Adobe Analytics.

## Utilisation de guillemets

La plupart des variables envoyées à Adobe sont des chaînes. Dans JavaScript, vous pouvez utiliser des guillemets simples ou doubles.

### Mixage de guillemets pour définir une variable

En règle générale, veillez à respecter les types de guillemets que vous utilisez. Si un guillemet simple désigne le début d’une chaîne, un guillemet simple doit être utilisé pour la fermer.

Par exemple, les deux `s.eVar1 = 'Value'` et `s.eVar1 = "Value"` sont valides. `s.eVar1 = 'Value"` n&#39;est pas valable.

### Inclusion de guillemets simples ou doubles dans une chaîne

Il est parfois souhaitable d’inclure un guillemet simple ou double dans une chaîne. Par exemple, vous souhaitez inclure la valeur `Alex's sale` ou `John the "Hunter"` dans les rapports. Il existe deux méthodes pour inclure ces valeurs :

* **Utilisez l’autre type** de guillemet :Par exemple, `s.eVar1 = "Alex's sale"` et `s.eVar1 = 'John the "Hunter"'` sont tous deux valides.
* **Echapper aux guillemets**: Utilisez une barre oblique inverse pour échapper les guillemets. Par exemple, `s.eVar1 = 'Alex\'s sale'` et `s.eVar1 = "John the \"Hunter\""` sont tous deux valides.

### Evitez d’utiliser des guillemets courbes.

Certains programmes convertissent automatiquement les guillemets neutres (`"..."` et `'...'`) en guillemets courbes (`“...”` et `‘...’`). Evitez d’utiliser des éditeurs de documents (tels que Microsoft Word) ou de transmettre des fragments de code par courrier électronique. Les guillemets courbes ne peuvent pas être utilisés dans JavaScript.

## Référence à l’objet Analytics

Toutes les variables envoyées à Adobe utilisent l’objet Analytics. La plupart des implémentations utilisent l’ `s` objet. Veillez à inclure l’objet Analytics dans votre référence lorsque vous référencez des variables.

Par exemple, `s.eVar1 = 'Value'` est valide, alors que `eVar1 = 'Value'` ne l’est pas.

## Définir chaque variable une fois

Lorsqu’une fonction de suivi (`s.t()`) s’exécute, AppMeasurement prend toutes les variables définies et les compile dans une demande d’image. Si vous définissez une variable plusieurs fois dans votre implémentation, seule la dernière valeur est utilisée. Assurez-vous que toutes les valeurs de variable contiennent la valeur correcte lors de l’exécution de la fonction track.

## Correction de la casse des variables

Certaines variables utilisent des lettres majuscules. Les variables JavaScript sont sensibles à la casse. Veillez à utiliser la casse correcte lors de la définition de variables. Par exemple, `s.eVar1 = 'Value'` est valide, alors que `s.evar1 = 'Value'` ne l’est pas.

## Modules externes

Certaines organisations utilisent des modules externes pour améliorer leur mise en oeuvre d’Adobe Analytics. Lors de la mise à niveau des versions d’AppMeasurement, n’oubliez pas de réinclure les modules externes installés. Le code créé dans le Gestionnaire [!UICONTROL de] code ne comporte aucun code de module externe. Effectuez une copie du code existant au cas où vous auriez besoin de revenir à une version précédente d’AppMeasurement.

## Espace blanc dans les valeurs de variable

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

In this case, `document.title` populates `s.pageName`, which receives a value of &quot;Home Page&quot;. Cependant, certains navigateurs peuvent interpréter l’espace blanc différemment. Le résultat peut être l’un des deux exemples suivants :

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

Ces deux valeurs de variable sont considérées comme distinctes dans Adobe Analytics. Toutefois, l’espace blanc est automatiquement supprimé à des fins d’affichage. Le résultat est un rapport qui affiche deux éléments de ligne &quot;Page d’accueil&quot; apparemment identiques. Assurez-vous que les valeurs de variable ne contiennent pas d’espace blanc avant ou après la valeur souhaitée.
