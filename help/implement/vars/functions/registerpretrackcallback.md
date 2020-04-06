---
title: registerPreTrackCallback
description: Permet de créer des fonctions de rappel avant d’envoyer un accès à Adobe.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# registerPreTrackCallback

La variable `registerPreTrackCallback` permet à votre entreprise d’associer une fonction JavaScript après la compilation d’une URL de demande d’image, mais avant son envoi. Vous pouvez utiliser cette variable pour envoyer les données collectées par AppMeasurement à un partenaire ou à une infrastructure interne.

>[!IMPORTANT] N’appelez pas d’appels de suivi comme [`t()`](t-method.md) ou [`tl()`](tl-method.md) à l’intérieur de la [`registerPostTrackCallback`](registerposttrackcallback.md) variable. Les fonctions de suivi de cette variable provoquent une boucle infinie de demandes d’image !

Chaque fois que vous appelez la variable `registerPreTrackCallback`, vous associez cette fonction pour qu’elle s’exécute chaque fois qu’une URL de demande d’image est compilée. Évitez d’enregistrer la même fonction plusieurs fois au même chargement de page.

>[!NOTE] Le timing et l’ordre des fonctions déclenchées entre `registerPreTrackCallback` et `registerPostTrackCallback` ne sont pas garantis. Évitez les dépendances entre ces deux fonctions.

## Enregistrement d’un rappel de pré-suivi dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Launch pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.registerPreTrackCallback dans AppMeasurement et l’éditeur de code personnalisé de Launch

La fonction `s.registerPreTrackCallback` prend une fonction comme son seul argument. La fonction imbriquée s’exécute juste avant l’envoi d’une demande d’image.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Si vous souhaitez utiliser l’URL de demande d’image dans votre code, référencez l’argument de chaîne `requestUrl` dans la fonction imbriquée. Vous pouvez analyser la variable `requestUrl` en fonction de l’utilisation souhaitée ; l’ajustement de cette variable n’a aucune incidence sur la collecte des données.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Vous pouvez inclure des arguments supplémentaires dans la `s.registerPreTrackCallback` fonction, qui peuvent être utilisés dans la fonction imbriquée :

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

>[!NOTE] La définition de variables de page ou la modification de la chaîne `requestUrl` dans cette fonction n’ont **pas** d’incidence sur la demande d’image envoyée peu après cet appel de fonction. Utilisez plutôt la [`doPlugins()`](doplugins.md) variable.
