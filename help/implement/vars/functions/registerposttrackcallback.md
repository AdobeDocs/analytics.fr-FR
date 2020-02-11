---
title: registerPostTrackCallback
description: Créez des fonctions de rappel après l’envoi d’un accès à Adobe.
translation-type: tm+mt
source-git-commit: acfcb1f27650649581875680e7897e5c9813765a

---


# registerPostTrackCallback

La `registerPostTrackCallback` variable permet à votre entreprise d’associer une fonction JavaScript immédiatement après l’envoi d’un accès à Adobe. Si un appel de suivi échoue, cette fonction ne s’exécute pas. Vous pouvez utiliser cette variable pour envoyer les données collectées par AppMeasurement à un partenaire ou à une infrastructure interne, ou nettoyer les valeurs de variable dans les applications d’une seule page.

> [!IMPORTANT] N’appelez aucune fonction de suivi telle `t` ou `tl` à l’intérieur de la `registerPostTrackCallback` variable. Les fonctions de suivi de cette variable provoquent une boucle infinie de demandes d’image !

Chaque fois que vous appelez la `registerPostTrackCallback` variable, vous pouvez associer cette fonction pour qu’elle s’exécute immédiatement après l’envoi réussi d’une demande d’image. Evitez d’enregistrer la même fonction plusieurs fois au même chargement de page.

> [!NOTE] Le timing et l&#39;ordre des fonctions déclenchées entre `registerPreTrackCallback` et `registerPostTrackCallback` ne sont pas garantis. Evitez les dépendances entre ces deux fonctions.

## Enregistrer le rappel de suivi de publication dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.registerPostTrackCallback dans AppMeasurement et lancement de l’éditeur de code personnalisé

La fonction `s.registerPostTrackCallback` prend une fonction comme son seul argument. La fonction imbriquée s’exécute juste avant l’envoi d’une demande d’image.

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

Si vous souhaitez utiliser l’URL de demande d’image dans votre code, référencez l’argument `requestUrl` string dans la fonction imbriquée. Vous pouvez analyser la `requestUrl` variable en fonction de l’utilisation souhaitée ; l’ajustement de cette variable n’a aucune incidence sur la collecte des données.

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Des arguments supplémentaires peuvent être inclus dans la `s.registerPostTrackCallback` fonction, qui peut être utilisée dans la fonction imbriquée :

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## Exemple de cas d&#39;utilisation

L’enregistrement de la `clearVars()` fonction dans le rappel de suivi de publication peut être bénéfique pour les applications d’une seule page. Chaque fois que vous envoyez un accès à Adobe, la `clearVars()` fonction s’exécute. Votre implémentation peut ensuite définir à nouveau des variables sans se soucier de la persistance incorrecte des valeurs.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
