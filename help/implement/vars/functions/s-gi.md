---
title: s_gi()
description: Permet de créer des instances d’AppMeasurement et d’en effectuer le suivi.
feature: Variables
exl-id: f87eff07-7e60-480b-8334-3db538c1030e
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 100%

---

# s_gi

La fonction `s_gi()` instancie ou trouve une instance d’AppMeasurement par identifiant de suite de rapports. AppMeasurement effectue le suivi de toutes les instances créées, tandis que la fonction `s_gi()` renvoie l’instance existante pour une suite de rapports, le cas échéant. S’il n’existe aucune instance, une nouvelle instance est créée.

## Instanciez un objet de suivi à l’aide de l’extension SDK Web

L’extension SDK Web instancie et gère l’objet de suivi à votre place. Cependant, vous pouvez personnaliser le nom de l’objet de suivi dans les paramètres d’extension :

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous le SDK Web d’Adobe Experience Platform.
1. Modifiez le champ [!UICONTROL Nom] sur la valeur souhaitée. Sa valeur par défaut est `alloy`.

## Instanciez un objet de suivi implémentant manuellement le SDK Web

Le code suivant charge le SDK Web et instancie un objet de suivi. Vous pouvez personnaliser le nom de l’objet de suivi en modifiant la chaîne `"alloy"` à la fin du script intégré sur la valeur souhaitée.

```js
<script>
  !function(n,o){o.forEach(function(o){n[o]||((n.__alloyNS=n.__alloyNS||
  []).push(o),n[o]=function(){var u=arguments;return new Promise(
  function(i,l){n[o].q.push([i,l,u])})},n[o].q=[])})}
  (window,["alloy"]);
</script>
<script src="https://cdn1.adoberesources.net/alloy/2.6.4/alloy.min.js" async></script>
```

Pour plus d’informations, voir la section [Installer le SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=fr) dans la documentation du SDK Web.

## Instanciez un objet de suivi à l’aide de l’extension Adobe Analytics

L’extension Analytics instancie et gère l’objet de suivi à votre place. Cependant, vous pouvez également définir un objet de suivi global dans l’accordéon [!UICONTROL Gestion des bibliothèques] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Gestion des bibliothèques], puis cochez une case autre que [!UICONTROL Gérer la bibliothèque pour moi].

Le champ de texte de variable globale vous permet de définir un objet de suivi personnalisé. Sa valeur par défaut est `s`.

## s_gi() dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Appelez la fonction `s_gi()` pour instancier un objet de suivi. Son seul argument contient une chaîne délimitée par des virgules d’identifiant de suite de rapports. L’argument d’identifiant de suite de rapports est obligatoire.

>[!TIP]
>
>Adobe recommande d’utiliser la variable `s` comme objet de suivi. Adobe utilise `s` dans sa documentation, ses exemples de mise en œuvre et ses plug-ins. Vous pouvez toutefois utiliser n’importe quelle variable tant que vous êtes cohérent sur l’ensemble de votre site.

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

>[!CAUTION]
>
>Les sections et exemples suivants contiennent des rubriques de mise en œuvre complexes. Testez minutieusement votre mise en œuvre et effectuez le suivi des personnalisations importantes dans le [document de conception de solution](../../prepare/solution-design.md) de votre organisation.

## Gestion de plusieurs mises en œuvre à l’aide de différents objets de suivi

Vous pouvez envoyer différentes données à différentes suites de rapports si vous instanciez plusieurs objets de suivi. Ces deux objets de suivi fonctionnent indépendamment l’un de l’autre.

```js
// Instantiate two separate tracking objects to two different report suites
var s = s_gi('examplersid1');
var z = s_gi('examplersid2');

// The s object and z object contain their own independent Analytics variables simultaneously
s.pageName = "Example page name 1";
z.pageName = "Example page name 2";

// Send data to the examplersid1 report suite
s.t();

// Send data to the examplersid2 report suite
z.t();
```

## Restauration des variables AppMeasurement après avoir remplacé l’objet s

Certains outils tiers peuvent également utiliser l’objet JavaScript `s`. Si vous écrasez accidentellement l’objet `s` sur votre site, vous pouvez appeler `s_gi` avec le même argument de chaîne RSID pour restaurer toutes les variables et méthodes remplacées.

```js
// Step 1: Instantiate the tracking object
var s = s_gi("examplersid");

// Step 2: Set eVar1
s.eVar1 = "Example value";

// Step 3: Accidentally overwrite the tracking object
s = "3rd party tool";

// Step 4: If you attempt to send a tracking call, an error is returned. Instead, re-instantiate the tracking object
s = s_gi("examplersid");

// Step 5: The previous values of all variables are preserved. You can send a tracking call and eVar1 is correctly set
s.t();
```

## Référencement du même objet de suivi avec plusieurs variables

Si deux variables font référence à la même fonction `s_gi()` avec la même suite de rapports, vous pouvez les utiliser de manière interchangeable.

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
