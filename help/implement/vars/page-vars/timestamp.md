---
title: timestamp
description: Permet de définir manuellement l’horodatage de l’accès.
feature: Variables
exl-id: 9d5ce5ef-2d84-4f65-b2e3-7aa3e219bc34
source-git-commit: a41fed835b6dcd3979111a7b13eaf33b63a3b2ec
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 81%

---

# timestamp

La variable `timestamp` définit manuellement l’horodatage de l’accès pour les suites de rapports horodatées.

>[!WARNING]
>
>N’utilisez pas cette variable si votre suite de rapports n’est pas explicitement configurée pour accepter les accès horodatés. AppMeasurement définit automatiquement l’heure d’un accès pour les suites de rapports qui ne prennent pas en charge les accès horodatés. Si vous envoyez un accès avec cette variable à une suite de rapports qui ne prend pas en charge les horodatages, ces données sont définitivement perdues.

## Horodatage à l’aide du SDK Web

Horodatage [mappé pour Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=fr) sous le champ XDM `xdm.timestamp`. Ce champ ne prend en charge que l’heure Unix.

## Horodatage à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.timestamp dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.timestamp` est une chaîne contenant la date et l’heure de l’accès. Les formats d’horodatage valides sont [ISO 8601](https://fr.wikipedia.org/wiki/ISO_8601) et [Heure Unix](https://fr.wikipedia.org/wiki/Heure_Unix).

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

* La date et l’heure doivent être précisées, séparées par `T`.
* Les heures et minutes sont requises ; les secondes sont facultatives, mais recommandées.
* Les dates de semaine et les dates ordinales ne sont pas prises en charge.
* La date peut être au format standard ou étendu. Par exemple, `2020-01-01T00:00:00Z` et `20200101T000000Z` sont tous deux valides.
* Les minutes et secondes fractionnaires sont techniquement valides, mais les fractions sont ignorées par Adobe.
* Les fuseaux horaires sont pris en charge dans les formats standard et étendus.

Voici des exemples de valeurs ISO 8601 valides dans la variable `timestamp` :

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
