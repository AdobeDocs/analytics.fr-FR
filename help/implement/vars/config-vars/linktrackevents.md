---
title: linkTrackEvents
description: Permet de déterminer les événements à inclure dans les demandes d’image de suivi de liens.
feature: Appmeasurement Implementation
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
role: Admin, Developer
TQID: https://experienceleague.adobe.com/7BKaDxchTRu39doWzm8f32DOemgpvj1s-4uzfjJkOEA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 325
ht-degree: 66%

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
