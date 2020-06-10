---
title: linkTrackVars
description: Permet de spécifier les variables à inclure dans les demandes d’image de suivi des liens.
translation-type: tm+mt
source-git-commit: a28a05047e95d12343fd94f7b11e5cabf7fac070
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 88%

---


# linkTrackVars

Certaines mises en œuvre ne souhaitent pas inclure toutes les variables dans toutes les demandes d’image de suivi de liens. Utilisez les variables `linkTrackVars` et [`linkTrackEvents`](linktrackevents.md) pour inclure de manière sélective des dimensions et des mesures dans les appels [`tl()`](../functions/tl-method.md).

This variable is not used for page view calls ([`t()`](../functions/t-method.md) method).

## Variables des appels de suivi de liens à l’aide d’Adobe Experience Platform Launch

Launch renseigne automatiquement cette variable sur le serveur principal en fonction des variables définies dans l’interface. Elle est donc toujours définie dans les mises en œuvre à l’aide de Launch.

>[!IMPORTANT] Si vous définissez des variables dans Launch à l’aide de l’éditeur de code personnalisé, vous devez également inclure la variable dans `linkTrackVars` à l’aide du code personnalisé.

## s.linkTrackVars dans AppMeasurement et l’éditeur de code personnalisé de Launch

The `s.linkTrackVars` variable is a string containing a comma-delimited list of variables that you want to include in link tracking image requests (`tl()` method). Les deux critères suivants doivent être satisfaits pour inclure des dimensions dans les accès de suivi des liens :

* Définissez la valeur de variable souhaitée. Par exemple : `s.eVar1 = "Example value";`.
* Définissez la variable souhaitée dans la variable `linkTrackVars`. Par exemple : `s.linkTrackVars = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

La valeur par défaut de cette variable est une chaîne vide. Adobe a toutefois fourni du code AppMeasurement dans le gestionnaire de code où cette variable est définie sur `"None"`. Les valeurs valides sont toutes les variables de niveau page qui renseignent une dimension.

* Si cette variable n’est pas définie ou définie sur une chaîne vide, *toutes* les variables sont incluses dans les demandes d’image de suivi des liens.
* Si cette variable est définie sur `"None"`, *aucune* variable n’est incluse dans les demandes d’image de suivi de lien.

>[!TIP] Évitez d’utiliser l’identifiant d’objet Analytics (`s.`) lors de la spécification de variables dans cette variable. Par exemple, `s.linkTrackVars = "eVar1";` est correct, alors que `s.linkTrackVars = "s.eVar1";` est incorrect.

## Exemple

La fonction de suivi des liens suivante inclut uniquement `eVar1` (et non `eVar2`) dans la demande d’image envoyée à Adobe :

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
