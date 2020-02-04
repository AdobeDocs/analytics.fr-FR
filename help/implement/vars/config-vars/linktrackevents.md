---
title: linkTrackEvents
description: Déterminez les événements à inclure dans les demandes d’image de suivi de liens.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkTrackEvents

Certaines implémentations ne souhaitent pas inclure toutes les variables dans toutes les demandes d’image de suivi de liens. Utilisez les `linkTrackVars` variables et `linkTrackEvents` pour inclure de manière sélective des dimensions et des mesures dans `tl()` les appels.

Cette variable n’est pas utilisée pour les appels de page vue (`t()` fonction).

## Evénements dans les appels de suivi de liens à l’aide d’Adobe Experience Platform Launch

Launch détecte automatiquement les événements définis dans l’interface et les inclut dans les accès de suivi de liens.

> [!IMPORTANT] Si vous définissez des événements dans Lancer à l’aide de l’éditeur de code personnalisé, vous devez inclure l’événement dans `linkTrackEvents` l’utilisation du code personnalisé.

## s.linkTrackEvents dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.linkTrackEvents` variable est une chaîne contenant une liste d’événements délimités par des virgules que vous souhaitez inclure dans les demandes d’image de suivi de liens (`tl()` fonction). Les trois critères suivants doivent être satisfaits pour inclure des mesures dans les accès de suivi des liens :

* Définissez l’événement souhaité dans la `events` variable. Par exemple : `s.events = "event1";`.
* Set the `events` variable in `linkTrackVars`. Par exemple : `s.linkTrackVars = "events";`.
* Définissez l’événement souhaité dans la `linkTrackEvents` variable. Par exemple : `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

La valeur par défaut de cette variable est une chaîne vide. Si cette variable n’est pas définie, tous les événements sont inclus dans les demandes d’image de suivi des liens. Notez que Launch renseigne automatiquement cette variable en fonction des événements définis dans l’interface ; il est donc toujours défini dans les implémentations à l’aide de Launch.

> [!TIP] Evitez d’utiliser l’identifiant d’objet Analytics (`s.`) lors de la spécification d’événements dans cette variable. Par exemple, `s.linkTrackEvents = "event1";` est correct, alors `s.linkTrackEvents = "s.event1";` qu’il est incorrect.

## Exemple

La fonction de suivi des liens suivante inclut uniquement `event1` (non `event2`) la demande d’image envoyée à Adobe :

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
