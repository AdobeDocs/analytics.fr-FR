---
title: s_gi()
description: Créez et effectuez le suivi des instances d’AppMeasurement.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# s_gi

La `s_gi()` fonction instancie ou trouve une instance d’AppMeasurement par identifiant de suite de rapports. AppMeasurement keeps track of every instance created, and `s_gi()` returns the existing instance for a report suite if one exists. Si une instance n’existe pas, une nouvelle instance est créée.

## s_gi() dans Adobe Experience Platform Launch

L’extension Analytics instancie et gère l’objet de suivi à votre place. Cependant, vous pouvez également définir un objet de suivi global dans l’ [!UICONTROL Library Management] accordéon lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Configure] bouton sous Adobe Analytics.
4. Développez l’ [!UICONTROL Library Management] accordéon, puis sélectionnez un bouton radio autre que [!UICONTROL Manage the library for me].

Le champ de texte de variable globale vous permet de définir un objet de suivi personnalisé. Its default value is `s`.

## s_gi() dans l’éditeur de code personnalisé AppMeasurement et Launch

Appelez la `s_gi()` fonction pour instancier un objet de suivi. Son seul argument contient une chaîne délimitée par des virgules d’ID de suite de rapports. L&#39;argument ID de suite de rapports est obligatoire.

> [!TIP] Adobe recommande d’utiliser la `s` variable comme objet de suivi. Adobe utilise `s` dans sa documentation, ses exemples d’implémentation et ses modules externes. Cependant, vous pouvez utiliser n’importe quelle variable tant que vous êtes cohérent sur l’ensemble de votre site.

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

> [!CAUTION] Les sections et exemples suivants contiennent des rubriques d’implémentation complexes. Testez minutieusement votre mise en oeuvre et effectuez le suivi des personnalisations importantes dans le de conception de [solution de votre entreprise](../../prepare/solution-design.md).

## Gestion de plusieurs implémentations à l’aide de différents objets de suivi

Vous pouvez envoyer différentes données à différentes suites de rapports si vous instanciez plusieurs objets de suivi. Ces deux objets de suivi fonctionnent indépendamment les uns des autres.

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

## Restaurer les variables AppMeasurement après avoir remplacé l’objet s

Certains outils tiers peuvent également utiliser l’objet JavaScript `s` . Si vous écrasez accidentellement l’ `s` objet sur votre site, vous pouvez appeler `s_gi` avec le même argument de chaîne RSID pour restaurer toutes les variables et méthodes remplacées.

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

## Référencer le même objet de suivi avec plusieurs variables

Si deux variables font référence à la même `s_gi()` fonction avec la même suite de rapports, vous pouvez les utiliser de manière interchangeable.

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
