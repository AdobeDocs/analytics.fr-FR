---
title: timestamp
description: Définissez manuellement l’horodatage de l’accès.
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# timestamp

La `timestamp` variable définit manuellement l’horodatage de l’accès pour les suites de rapports horodatées.

> [!WARNING] N’utilisez pas cette variable si votre suite de rapports n’est pas explicitement configurée pour accepter les accès horodatés. AppMeasurement définit automatiquement l’heure d’un accès pour les suites de rapports qui ne prennent pas en charge les accès horodatés. Si vous envoyez un accès avec cette variable à une suite de rapports qui ne prend pas en charge les horodatages, ces données sont définitivement perdues.

## Horodatage dans le lancement d’Adobe Experience Platform

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.timestamp dans AppMeasurement et Lancement de l’éditeur de code personnalisé

La `s.timestamp` variable est une chaîne contenant la date et l’heure de l’accès. Les formats d’horodatage valides sont [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) et [Unix time](https://en.wikipedia.org/wiki/Unix_time).

```js
// Timestamp using ISO 8601
s.timestamp = "2020-01-01T00:00:00Z";

// Timestamp using Unix timestamp
s.timestamp = "1577836800";

// Automatically get the current Unix timestamp
s.timestamp = Math.round(new Date().getTime()/1000);

// Automatically get the current ISO 8601 timestamp
s.timestamp = new Date().toISOString();
```

## Valeurs ISO 8601

Les dates et les heures exprimées dans la [norme ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) peuvent prendre différentes formes. Adobe ne prend pas en charge toutes les fonctionnalités de la norme ISO 8601.

* Both the date and time must be provided, separated by `T`.
* Heures et minutes sont requises; secondes sont facultatives, mais recommandées.
* Les dates de semaine et les dates ordinales ne sont pas prises en charge.
* La date peut être au format standard ou étendu. Par exemple, `2020-01-01T00:00:00Z` et `20200101T000000Z` sont tous deux valides.
* Les minutes et secondes fractionnaires sont techniquement valides, mais les fractions sont ignorées par Adobe.
* Les fuseaux horaires sont pris en charge dans les formats standard et étendus.

Voici des exemples de valeurs ISO 8601 valides dans la `timestamp` variable :

```text
2020-01-01T00:00:00+00:00
2020-01-01T00:00:00Z
2020-01-01T00:00:00
2020-01-01T00:00
20200101T000000+0000
20200101T000000Z
20200101T000000
20200101T0000
```
