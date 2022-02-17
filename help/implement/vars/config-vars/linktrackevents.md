---
title: linkTrackEvents
description: Permet de déterminer les événements à inclure dans les demandes d’image de suivi de liens.
feature: Variables
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 100%

---

# linkTrackEvents

Certaines mises en œuvre ne souhaitent pas inclure toutes les variables dans toutes les demandes d’image de suivi de liens. Utilisez les variables [`linkTrackVars`](linktrackvars.md) et `linkTrackEvents` pour inclure de manière sélective des dimensions et des mesures dans les appels [`tl()`](../functions/tl-method.md).

Cette variable n’est pas utilisée pour les appels de page vue (méthode [`t()`](../functions/t-method.md)).

## Événements dans les appels de suivi des liens à l’aide de balises dans Adobe Experience Platform

Adobe Experience Platform inclut automatiquement les événements définis dans les accès de suivi des liens si vous n’utilisez pas de code personnalisé.

>[!IMPORTANT]
>
>Si vous définissez des événements dans l’interface utilisateur de la collecte de données à l’aide de l’éditeur de code personnalisé, vous devez inclure l’événement dans `linkTrackEvents` en utilisant également le code personnalisé.

## s.linkTrackEvents dans AppMeasurement et l’éditeur de code personnalisé

La variable `s.linkTrackEvents` est une chaîne contenant une liste d’événements délimitée par des virgules que vous souhaitez inclure dans les demandes d’image de suivi de liens (méthode `tl()`). Les trois critères suivants doivent être satisfaits pour inclure des mesures dans les accès de suivi des liens :

* Définissez l’événement souhaité dans la variable [`events`](../page-vars/events/events-overview.md). Par exemple : `s.events = "event1";`.
* Définissez la variable `events` dans `linkTrackVars`. Par exemple : `s.linkTrackVars = "events";`.
* Définissez l’événement souhaité dans la variable `linkTrackEvents`. Par exemple : `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

La valeur par défaut de cette variable est une chaîne vide. Si cette variable n’est pas définie, tous les événements sont inclus dans les demandes d’image de suivi des liens. Notez que la collecte de données renseigne automatiquement cette variable en fonction des événements définis dans l’interface. Elle est donc toujours définie pour les implémentations qui utilisent des balises dans Adobe Experience Platform.

>[!TIP]
>
>Évitez d’utiliser l’identifiant d’objet Analytics (`s.`) lors de la spécification d’événements dans cette variable. Par exemple, `s.linkTrackEvents = "event1";` est correct, alors que `s.linkTrackEvents = "s.event1";` est incorrect.

## Exemple

La fonction de suivi des liens suivante inclut uniquement `event1` (et non `event2`) dans la demande d’image envoyée à Adobe :

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
