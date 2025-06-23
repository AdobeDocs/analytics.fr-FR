---
title: linkTrackVars
description: Permet de spécifier les variables à inclure dans les demandes d’image de suivi des liens.
feature: Appmeasurement Implementation
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 62%

---

# linkTrackVars

Certaines mises en œuvre ne souhaitent pas inclure toutes les variables dans toutes les demandes d’image de suivi de liens. Utilisez les variables `linkTrackVars` et [`linkTrackEvents`](linktrackevents.md) pour inclure de manière sélective des dimensions et des mesures dans les appels [`tl()`](../functions/tl-method.md).

Cette variable n’est pas utilisée pour les appels de page vue (méthode [`t()`](../functions/t-method.md)).

## Déterminer les variables à inclure dans un événement XDM à l’aide de Web SDK

Le Web SDK n’exclut pas certains champs pour les appels de suivi des liens. Cependant, vous pouvez utiliser le rappel `onBeforeEventSend` pour effacer ou définir les champs souhaités avant l’envoi des données à Adobe. Voir [Modifier globalement les événements](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) dans la documentation de Web SDK pour plus d’informations.

## Variables dans les appels de suivi des liens à l’aide de l’extension Adobe Analytics

Cette variable est automatiquement renseignée sur le serveur principal en fonction des variables définies dans l’interface. Elle est donc toujours définie dans les implémentations à l’aide de l’extension Adobe Analytics.

>[!IMPORTANT]
>
>Si vous définissez des variables à l’aide de l’éditeur de code personnalisé, vous devez également inclure la ou les variables dans `linkTrackVars` à l’aide du code personnalisé.

## s.linkTrackVars dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.linkTrackVars` est une chaîne contenant une liste de variables délimitées par des virgules que vous souhaitez inclure dans les demandes d’image de suivi de liens (méthode `tl()`). Les deux critères suivants doivent être satisfaits pour inclure des dimensions dans les accès de suivi des liens :

* Définissez la valeur de variable souhaitée. Par exemple : `s.eVar1 = "Example value";`.
* Définissez la variable souhaitée dans la variable `linkTrackVars`. Par exemple : `s.linkTrackVars = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

La valeur par défaut de cette variable est une chaîne vide. Adobe a toutefois fourni du code AppMeasurement dans le gestionnaire de code où cette variable est définie sur `"None"`. Les valeurs valides sont toutes les variables de niveau page qui renseignent une dimension.

* Si cette variable n’est pas définie ou définie sur une chaîne vide, *toutes* les variables sont incluses dans les demandes d’image de suivi des liens.
* Si cette variable est définie sur `"None"`, *aucune* variable n’est incluse dans les demandes d’image de suivi de lien.

>[!TIP]
>
>Évitez d’utiliser l’identifiant d’objet Analytics (`s.`) lors de la spécification de variables dans cette variable. Par exemple, `s.linkTrackVars = "eVar1";` est correct, alors que `s.linkTrackVars = "s.eVar1";` est incorrect.

## Exemple

La fonction de suivi des liens suivante inclut uniquement `eVar1` (et non `eVar2`) dans la demande d’image envoyée à Adobe :

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
