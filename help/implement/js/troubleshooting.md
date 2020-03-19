---
title: Résolution des problèmes de mise en œuvre de JavaScript
description: Découvrez les problèmes courants et les bonnes pratiques pour résoudre les problèmes de votre mise en œuvre JavaScript.
translation-type: ht
source-git-commit: 8aa6932dcbb6dad88c27ba1cd4f5aad3bafcfc52

---


# Résolution des problèmes de mise en œuvre de JavaScript

Vous trouverez ci-dessous plusieurs raisons pour lesquelles votre organisation peut rencontrer des problèmes lors de l’importation correcte des données dans Adobe Analytics.

## Utilisation de guillemets

La plupart des variables envoyées à Adobe sont des chaînes. Dans JavaScript, vous pouvez utiliser des guillemets simples ou doubles.

### Mixage de guillemets pour définir une variable

En règle générale, veillez à respecter les types de guillemets que vous utilisez. Si un guillemet simple désigne le début d’une chaîne, un guillemet simple doit être utilisé pour la fermer.

Par exemple, les deux `s.eVar1 = 'Value'` et `s.eVar1 = "Value"` sont valides. `s.eVar1 = 'Value"` n’est pas valide.

### Inclusion de guillemets simples ou doubles dans une chaîne

Il est parfois souhaitable d’inclure un guillemet simple ou double dans une chaîne. Par exemple, vous souhaitez inclure la valeur `Alex's sale` ou `John the "Hunter"` dans les rapports. Il existe deux méthodes pour inclure ces valeurs :

* **Utilisez l’autre type de guillemet** : par exemple, `s.eVar1 = "Alex's sale"` et `s.eVar1 = 'John the "Hunter"'` sont tous deux valides.
* **Échapper les guillemets** : utilisez une barre oblique inverse pour échapper les guillemets. Par exemple, `s.eVar1 = 'Alex\'s sale'` et `s.eVar1 = "John the \"Hunter\""` sont tous deux valides.

### Évitez d’utiliser des guillemets courbes.

Certains programmes convertissent automatiquement les guillemets neutres (`"..."` et `'...'`) en guillemets courbes (`“...”` et `‘...’`). Évitez d’utiliser des éditeurs de documents (tels que Microsoft Word) ou de transmettre des fragments de code par courrier électronique. Les guillemets courbes ne peuvent pas être utilisés dans JavaScript.

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
