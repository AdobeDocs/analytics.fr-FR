---
title: forceOnline
description: Définissez manuellement l’état en ligne d’AppMeasurement.
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# forceOnline

La `forceOnline` méthode vous permet de remplacer l’état d’AppMeasurement détecté automatiquement.

> [!IMPORTANT] N&#39;utilisez cette fonction que lorsque `trackOffline` est activé. L’utilisation de cette fonction en dehors du suivi hors ligne peut entraîner une perte de données.

AppMeasurement détecte automatiquement l’état en ligne du périphérique. Vous pouvez utiliser la `forceOnline` méthode pour forcer AppMeasurement à traiter les accès comme si l’appareil était en ligne. Cette méthode ne prend aucun argument et ne renvoie aucune valeur. Son seul objectif est de remplacer l’état en ligne dans AppMeasurement.

## Forcer en ligne dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.forceOnline() dans AppMeasurement et lancement de l’éditeur de code personnalisé

Vous pouvez appeler la `s.forceOnline()` méthode n’importe où dans votre implémentation après avoir appelé l’objet Analytics.

```js
s.forceOnline();
```
