---
title: registerPostTrackCallback
description: Permet de créer des fonctions de rappel après l’envoi d’un accès à Adobe.
translation-type: tm+mt
source-git-commit: 0d7e7dcb2cc382d83e267e51b1abeff38da270d3
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 95%

---


# registerPostTrackCallback

La variable `registerPostTrackCallback` permet à votre entreprise d’associer une fonction JavaScript immédiatement après l’envoi d’un accès à Adobe. Si un appel de suivi échoue, cette fonction ne s’exécute pas. Vous pouvez utiliser cette variable pour envoyer les données collectées par AppMeasurement à un partenaire ou à une infrastructure interne, ou nettoyer les valeurs de variable dans les applications d’une seule page.

>[!IMPORTANT] N’appelez aucun appel de suivi tel que [`t()`](t-method.md) ou [`tl()`](tl-method.md) à l’intérieur de la variable `registerPostTrackCallback`. Les fonctions de suivi de cette variable provoquent une boucle infinie de demandes d’image !

Chaque fois que vous appelez la variable `registerPostTrackCallback`, vous pouvez associer cette fonction pour qu’elle s’exécute immédiatement après l’envoi réussi d’une demande d’image. Évitez d’enregistrer la même fonction plusieurs fois au même chargement de page.

>[!NOTE] Le timing et l’ordre des fonctions déclenchées entre [`registerPreTrackCallback`](registerpretrackcallback.md) et `registerPostTrackCallback` ne sont pas garantis. Évitez les dépendances entre ces deux fonctions.

## Enregistrement d’un rappel de suivi de publication dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Launch pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.registerPostTrackCallback dans AppMeasurement et l’éditeur de code personnalisé de Launch

La fonction `s.registerPostTrackCallback` prend une fonction comme son seul argument. La fonction imbriquée s’exécute immédiatement après l’envoi d’une demande d’image.

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

Si vous souhaitez utiliser l’URL de demande d’image dans votre code, référencez l’argument de chaîne `requestUrl` dans la fonction imbriquée. Vous pouvez analyser la variable `requestUrl` en fonction de l’utilisation souhaitée ; l’ajustement de cette variable n’a aucune incidence sur la collecte des données.

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Des arguments supplémentaires peuvent être inclus dans la fonction `s.registerPostTrackCallback`, qui peut être utilisée dans la fonction imbriquée :

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## Exemple de cas d’utilisation

L’enregistrement de la fonction [`clearVars()`](clearvars.md) dans le rappel de suivi de publication peut être bénéfique pour les applications d’une seule page. Chaque fois que vous envoyez un accès à Adobe, la fonction `clearVars()` s’exécute. Votre mise en œuvre peut ensuite définir à nouveau des variables sans se soucier de la persistance incorrecte des valeurs.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
