---
title: linkTrackEvents
description: Déterminez le à inclure dans les demandes d’image de suivi de liens.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkTrackEvents

Certaines implémentations ne souhaitent pas inclure toutes les variables dans toutes les demandes d’image de suivi de liens. Utilisez les [`linkTrackVars`](linktrackvars.md) variables et `linkTrackEvents` pour inclure de manière sélective des dimensions et des mesures dans [`tl()`](../functions/tl-method.md) les appels.

Cette variable n’est pas utilisée pour les appels de  de page ([`t()`](../functions/t-method.md) méthode).

##  dans les appels de suivi de liens à l’aide d’Adobe Experience Platform Launch

Launch détecte automatiquement les  définies dans l’interface et les inclut dans les accès de suivi de liens.

> [!IMPORTANT] Si vous définissez  dans Lancer à l’aide de l’éditeur de code personnalisé, vous devez également inclure le dans l’ `linkTrackEvents` utilisation du code personnalisé.

## s.linkTrackEvents dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.linkTrackEvents` variable est une chaîne contenant un de délimités par des virgules que vous souhaitez inclure dans les demandes d’image de suivi de liens (`tl()` méthode). Les trois critères suivants doivent être satisfaits pour inclure des mesures dans les accès de suivi des liens :

* Définissez le  de souhaité dans la [`events`](../page-vars/events/events-overview.md) variable. Par exemple : `s.events = "event1";`.
* Set the `events` variable in `linkTrackVars`. Par exemple : `s.linkTrackVars = "events";`.
* Définissez le  de souhaité dans la `linkTrackEvents` variable. Par exemple : `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

La valeur par défaut de cette variable est une chaîne vide. Si cette variable n’est pas définie, tous les  de sont inclus dans les demandes d’image de suivi de liens. Notez que Launch renseigne automatiquement cette variable en fonction des  de définis dans l’interface. Il est donc toujours défini dans les implémentations à l’aide de Launch.

> [!TIP] Evitez d’utiliser l’identifiant d’objet Analytics (`s.`) lors de la spécification d’ d’dans cette variable. Par exemple, `s.linkTrackEvents = "event1";` est correcte, alors `s.linkTrackEvents = "s.event1";` qu’elle est incorrecte.

## Exemple

La fonction de suivi des liens suivante inclut uniquement `event1` (non `event2`) la demande d’image envoyée à Adobe :

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
