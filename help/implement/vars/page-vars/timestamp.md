---
title: timestamp
description: Permet de définir manuellement l’horodatage de l’accès.
feature: Appmeasurement Implementation
exl-id: 9d5ce5ef-2d84-4f65-b2e3-7aa3e219bc34
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 81%

---

# timestamp

La variable `timestamp` définit manuellement l’horodatage de l’accès pour les suites de rapports horodatées.

>[!WARNING]
>
>N’utilisez pas cette variable si votre suite de rapports n’est pas explicitement configurée pour accepter les accès horodatés. AppMeasurement définit automatiquement l’heure d’un accès pour les suites de rapports qui ne prennent pas en charge les accès horodatés. Si vous envoyez un accès avec cette variable à une suite de rapports qui ne prend pas en charge les horodatages, ces données sont définitivement perdues.

## Horodatage à l’aide de Web SDK

La date et l’heure sont [mappées pour Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/xdm-var-mapping.html) sous le `xdm.timestamp` de champ XDM. Ce champ prend uniquement en charge l’heure Unix.

## Horodatage à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.timestamp dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.timestamp` est une chaîne contenant la date et l’heure de l’accès. Les formats d’horodatage valides comprennent [ISO 8601](https://fr.wikipedia.org/wiki/ISO_8601) et [heure Unix](https://fr.wikipedia.org/wiki/Heure_Unix) en secondes.

```js
// Timestamp using ISO 8601
s.timestamp = "2024-01-01T00:00:00Z";

// Timestamp using Unix timestamp
s.timestamp = "1577836800";

// Automatically get the current Unix timestamp
s.timestamp = Math.round(new Date().getTime()/1000);

// Automatically get the current ISO 8601 timestamp
s.timestamp = new Date().toISOString();
```

## Valeurs ISO 8601

Les dates et les heures exprimées dans la [norme ISO 8601](https://fr.wikipedia.org/wiki/ISO_8601) peuvent prendre différentes formes. Adobe ne prend pas en charge toutes les fonctionnalités de la norme ISO 8601.

* La date et l’heure doivent être précisées, séparées par `T`.
* Les heures et minutes sont requises ; les secondes sont facultatives, mais recommandées.
* Les dates de semaine et les dates ordinales ne sont pas prises en charge.
* La date peut être au format standard ou étendu. Par exemple, `2024-01-01T00:00:00Z` et `20240101T000000Z` sont tous deux valides.
* Les minutes et secondes fractionnaires sont techniquement valides, mais les fractions sont ignorées par Adobe.
* Les fuseaux horaires sont pris en charge dans les formats standard et étendus.

Voici des exemples de valeurs ISO 8601 valides dans la variable `timestamp` :

```text
2024-01-01T00:00:00+00:00
2024-01-01T00:00:00Z
2024-01-01T00:00:00
2024-01-01T00:00
20240101T000000+0000
20240101T000000Z
20240101T000000
20240101T0000
```
