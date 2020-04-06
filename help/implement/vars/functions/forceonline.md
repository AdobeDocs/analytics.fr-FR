---
title: forceOnline
description: Permet de définir manuellement l’état en ligne d’AppMeasurement.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# forceOnline

La méthode `forceOnline()` vous permet de remplacer l’état d’AppMeasurement détecté automatiquement.

>[!IMPORTANT] N’utilisez cette méthode que lorsque [`trackOffline`](../config-vars/trackoffline.md) elle est activée. L’utilisation de cette fonction en dehors du suivi hors ligne peut entraîner une perte de données.

AppMeasurement détecte automatiquement l’état en ligne de l’appareil. Vous pouvez utiliser la méthode `forceOnline()` pour forcer AppMeasurement à traiter les accès comme si l’appareil était en ligne. Cette méthode ne prend aucun argument et ne renvoie aucune valeur. Son seul objectif est de remplacer l’état en ligne dans AppMeasurement.

## Forcer l’état en ligne dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Launch pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.forceOnline() dans AppMeasurement et l’éditeur de code personnalisé de Launch

Vous pouvez appeler la méthode `s.forceOnline()` n’importe où dans votre mise en œuvre après avoir appelé l’objet Analytics.

```js
s.forceOnline();
```
