---
title: forceOffline
description: Définissez manuellement l’état en ligne d’AppMeasurement.
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# forceOffline

La `forceOffline` méthode vous permet de remplacer l’état d’AppMeasurement détecté automatiquement.

> [!IMPORTANT] N&#39;utilisez cette fonction que lorsque `trackOffline` est activé. L’utilisation de cette fonction en dehors du suivi hors ligne peut entraîner une perte de données.

AppMeasurement détecte automatiquement l’état en ligne du périphérique. Vous pouvez utiliser la `forceOffline` méthode pour forcer AppMeasurement à traiter les accès comme si l’appareil était hors ligne. Cette méthode ne prend aucun argument et ne renvoie aucune valeur. Son seul objectif est de remplacer l’état en ligne dans AppMeasurement.

## Forcer le lancement hors ligne d’Adobe Experience Platform

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.forceOffline() dans l’éditeur de code personnalisé AppMeasurement et de lancement

Vous pouvez appeler la `s.forceOffline()` méthode n’importe où dans votre implémentation après avoir appelé l’objet Analytics.

```js
s.forceOffline();
```
