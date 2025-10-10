---
title: linkTrackEvents
description: Permet de déterminer les événements à inclure dans les demandes d’image de suivi de liens.
feature: Appmeasurement Implementation
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 68%

---

# linkTrackEvents

Certaines mises en œuvre ne souhaitent pas inclure toutes les variables dans toutes les demandes d’image de suivi de liens. Utilisez les variables [`linkTrackVars`](linktrackvars.md) et `linkTrackEvents` pour inclure de manière sélective des dimensions et des mesures dans les appels [`tl()`](../functions/tl-method.md).

Cette variable n’est pas utilisée pour les appels de page vue (méthode [`t()`](../functions/t-method.md)).

## Déterminer les événements Analytics à inclure dans un événement XDM à l’aide de Web SDK

Le Web SDK n’exclut pas certains champs pour les appels de suivi des liens. Cependant, vous pouvez utiliser le rappel `onBeforeEventSend` pour effacer ou définir les champs souhaités avant l’envoi des données à Adobe. Voir [Modifier globalement les événements](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=fr#modifying-events-globally) dans la documentation de Web SDK pour plus d’informations.

## Événements dans les appels de suivi des liens à l’aide de l’extension Adobe Analytics

Adobe Experience Platform inclut automatiquement les événements définis dans les accès de suivi des liens si vous n’utilisez pas de code personnalisé.

>[!IMPORTANT]
>
>Si vous définissez des événements dans l’éditeur de code personnalisé de l’extension Analytics, vous devez inclure l’événement dans `linkTrackEvents` à l’aide du code personnalisé également.

## s.linkTrackEvents dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

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
