---
title: registerPreTrackCallback
description: Permet de créer des fonctions de rappel avant d’envoyer un accès à Adobe.
feature: Variables
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
source-git-commit: 12d35a0f503ef79eabd55c169d9642c049542798
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 58%

---

# registerPreTrackCallback

La variable `registerPreTrackCallback` permet à votre entreprise d’associer une fonction JavaScript après la compilation d’une URL de demande d’image, mais avant son envoi. Vous pouvez utiliser cette variable pour envoyer les données collectées par AppMeasurement à un partenaire ou à une infrastructure interne.

>[!WARNING]
>
>N’effectuez aucun appel de suivi comme [`t()`](t-method.md) ou [`tl()`](tl-method.md) dans la variable `registerPreTrackCallback` Variable . La définition des appels de suivi dans cette variable entraîne une boucle infinie de demandes d’image.

Chaque fois que vous appelez la variable `registerPreTrackCallback`, vous associez cette fonction pour qu’elle s’exécute chaque fois qu’une URL de demande d’image est compilée. Évitez d’enregistrer la même fonction plusieurs fois au même chargement de page.

>[!NOTE]
>
>Le timing et l’ordre des fonctions déclenchées entre `registerPreTrackCallback` et `registerPostTrackCallback` ne sont pas garantis. Évitez les dépendances entre ces deux fonctions.

## Rappel de pré-suivi à l’aide de l’extension SDK Web

Le SDK Web ne peut pas associer une fonction une fois les données compilées, mais avant leur envoi à Adobe. Cependant, vous pouvez utiliser `onBeforeEventSend` pour enregistrer une fonction à exécuter juste avant l’envoi des données.

1. Connectez-vous au [Collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) de l’interface utilisateur à l’aide de vos identifiants Adobe ID ;
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]**[!UICONTROL  sous le SDK Web d’Adobe Experience Platform].
1. Sous [!UICONTROL Collecte de données], cliquez sur le **[!UICONTROL Modifier avant le code de rappel d’envoi d’événement]** bouton .
1. Placez le code de votre choix dans l’éditeur.

## Rappel de pré-suivi implémentant manuellement le SDK Web

Le SDK Web ne peut pas associer une fonction une fois les données compilées, mais avant leur envoi à Adobe. Cependant, vous pouvez utiliser `onBeforeEventSend` pour enregistrer une fonction à exécuter juste avant l’envoi des données, comme `doPlugins`. Voir [Modification globale des événements](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) pour plus d’informations, voir la documentation du SDK Web .

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Rappel de pré-suivi à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.registerPreTrackCallback dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

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
