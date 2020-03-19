---
title: linkTrackVars
description: Spécifiez les variables à inclure dans les demandes d’image de suivi des liens.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkTrackVars

Certaines implémentations ne souhaitent pas inclure toutes les variables dans toutes les demandes d’image de suivi de liens. Utilisez les `linkTrackVars` variables et [`linkTrackEvents`](linktrackevents.md) pour inclure de manière sélective des dimensions et des mesures dans [`tl()`](../functions/tl-method.md) les appels.

Cette variable n’est pas utilisée pour les appels de  de page (`t()` méthode).

## Variables des appels de suivi de liens à l’aide d’Adobe Experience Platform Launch

Launch renseigne automatiquement cette variable sur le serveur principal en fonction des variables définies dans l’interface. Elle est donc toujours définie dans les implémentations à l’aide de Launch.

> [!IMPORTANT] Si vous définissez des variables dans Lancer à l’aide de l’éditeur de code personnalisé, vous devez également inclure la variable dans `linkTrackVars` l’utilisation du code personnalisé.

## s.linkTrackVars dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.linkTrackVars` variable est une chaîne contenant un délimité par des virgules de variables que vous souhaitez inclure dans les demandes d’image de suivi de liens (`tl()` méthode). Les deux critères suivants doivent être satisfaits pour inclure des dimensions dans les accès de suivi des liens :

* Définissez la valeur de variable souhaitée. Par exemple : `s.eVar1 = "Example value";`.
* Définissez la variable souhaitée dans la `linkTrackVars` variable. Par exemple : `s.linkTrackEvents = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

La valeur par défaut de cette variable est une chaîne vide. Adobe a toutefois fourni du code AppMeasurement dans le Gestionnaire de code où cette variable est définie sur `"None"`. Les valeurs valides sont toutes les variables de niveau page qui renseignent une dimension.

* Si cette variable n’est pas définie ou définie sur une chaîne vide, *toutes les* variables sont incluses dans les demandes d’image de suivi des liens.
* Si cette variable est définie sur `"None"`, *aucune* variable n’est incluse dans les demandes d’image de suivi de lien.

> [!TIP] Evitez d’utiliser l’identifiant d’objet Analytics (`s.`) lors de la spécification de variables dans cette variable. Par exemple, `s.linkTrackVars = "eVar1";` est correcte, alors `s.linkTrackVars = "s.eVar1";` qu’elle est incorrecte.

## Exemple

La fonction de suivi des liens suivante inclut uniquement `eVar1` (non `eVar2`) la demande d’image envoyée à Adobe :

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
