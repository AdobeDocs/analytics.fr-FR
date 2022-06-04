---
title: registerPreTrackCallback
description: Permet de créer des fonctions de rappel avant d’envoyer un accès à Adobe.
feature: Variables
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 100%

---

# registerPreTrackCallback

La variable `registerPreTrackCallback` permet à votre entreprise d’associer une fonction JavaScript après la compilation d’une URL de demande d’image, mais avant son envoi. Vous pouvez utiliser cette variable pour envoyer les données collectées par AppMeasurement à un partenaire ou à une infrastructure interne.

>[!WARNING]
>
> N’appelez aucun appel de suivi tel que [`t()`](t-method.md) ou [`tl()`](tl-method.md) à l’intérieur de la variable [`registerPostTrackCallback`](registerposttrackcallback.md). Les fonctions de suivi de cette variable provoquent une boucle infinie de demandes d’image !

Chaque fois que vous appelez la variable `registerPreTrackCallback`, vous associez cette fonction pour qu’elle s’exécute chaque fois qu’une URL de demande d’image est compilée. Évitez d’enregistrer la même fonction plusieurs fois au même chargement de page.

>[!NOTE]
>
>Le timing et l’ordre des fonctions déclenchées entre `registerPreTrackCallback` et `registerPostTrackCallback` ne sont pas garantis. Évitez les dépendances entre ces deux fonctions.

## Enregistrement d’un rappel de pré-suivi à l’aide de balises dans Adobe Experience Platform

Il n’existe pas de champ dédié dans l’interface utilisateur de la collecte de données pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.registerPreTrackCallback dans AppMeasurement et l’éditeur de code personnalisé

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

Vous pouvez inclure des arguments supplémentaires dans la fonction `s.registerPreTrackCallback`, qui peuvent être utilisés dans la fonction imbriquée :

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

>[!NOTE]
>
>La définition de variables de page ou la modification de la chaîne `requestUrl` dans cette fonction n’ont **pas** d’incidence sur la demande d’image envoyée peu après cet appel de fonction. Utilisez plutôt la variable [`doPlugins()`](doplugins.md).
