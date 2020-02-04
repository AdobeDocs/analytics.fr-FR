---
title: registerPreTrackCallback
description: Créez des fonctions de rappel avant d’envoyer un accès à Adobe.
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# registerPreTrackCallback

La `registerPreTrackCallback` variable permet à votre entreprise d’associer une fonction JavaScript après la compilation d’une URL de demande d’image, mais avant son envoi. Vous pouvez utiliser cette variable pour envoyer les données collectées par AppMeasurement à un partenaire ou à une infrastructure interne.

> [!IMPORTANT] N’appelez aucune fonction de suivi telle `t` ou `tl` à l’intérieur de la `registerPostTrackCallback` variable. Les fonctions de suivi de cette variable provoquent une boucle infinie de demandes d’image !

Chaque fois que vous appelez la `registerPreTrackCallback` variable, vous associez cette fonction pour qu’elle s’exécute chaque fois qu’une URL de demande d’image est compilée. Evitez d’enregistrer la même fonction plusieurs fois au même chargement de page.

> [!NOTE] Le timing et l&#39;ordre des fonctions déclenchées entre `registerPreTrackCallback` et `registerPostTrackCallback` ne sont pas garantis. Evitez les dépendances entre ces deux fonctions.

## Enregistrer le rappel de pré-suivi dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.registerPreTrackCallback dans AppMeasurement et lancement de l’éditeur de code personnalisé

La fonction `s.registerPreTrackCallback` prend une fonction comme son seul argument. La fonction imbriquée s’exécute juste avant l’envoi d’une demande d’image.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Si vous souhaitez utiliser l’URL de demande d’image dans votre code, référencez l’argument `requestUrl` string dans la fonction imbriquée. Vous pouvez analyser la `requestUrl` variable en fonction de l’utilisation souhaitée ; l’ajustement de cette variable n’a aucune incidence sur la collecte des données.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Des arguments supplémentaires peuvent être inclus dans la `s.registerPreTrackCallback` fonction, qui peut être utilisée dans la fonction imbriquée :

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

> [!NOTE] La définition de variables de page ou la modification de la `requestUrl` chaîne dans cette fonction n’ont *pas* d’incidence sur la demande d’image envoyée peu après cet appel de fonction.
