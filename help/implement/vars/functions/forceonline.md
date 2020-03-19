---
title: forceOnline
description: Définissez manuellement l’état en ligne d’AppMeasurement.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# forceOnline

La `forceOnline()` méthode vous permet de remplacer l’état d’AppMeasurement détecté automatiquement.

> [!IMPORTANT] N’utilisez cette méthode que lorsque [`trackOffline`](../config-vars/trackoffline.md) elle est activée. L’utilisation de cette fonction en dehors du suivi hors ligne peut entraîner une perte de données.

AppMeasurement détecte automatiquement l’état en ligne du périphérique. Vous pouvez utiliser la `forceOnline()` méthode pour forcer AppMeasurement à traiter les accès comme si l’appareil était en ligne. Cette méthode ne prend aucun argument et ne renvoie aucune valeur. Son seul objectif est de remplacer l’état en ligne dans AppMeasurement.

## Forcer en ligne dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.forceOnline() dans AppMeasurement et lancement de l’éditeur de code personnalisé

Vous pouvez appeler la `s.forceOnline()` méthode n’importe où dans votre implémentation après avoir appelé l’objet Analytics.

```js
s.forceOnline();
```
