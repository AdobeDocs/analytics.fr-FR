---
title: offlineThrottleDelay
description: Permet de définir la fréquence des accès lorsqu’un appareil revient en ligne.
translation-type: ht
source-git-commit: f313fd0c9ffda054a18ad1d457a74602b08e51fa

---


# offlineThrottleDelay

Le suivi hors ligne est une méthode facultative de collecte de données dans Adobe Analytics. Si un visiteur se déconnecte d’Internet mais continue à parcourir votre site, les accès sont stockés dans une file d’attente hors ligne jusqu’à ce que l’appareil se reconnecte à Internet. Le suivi hors ligne est principalement utilisé pour les applications mobiles.

Lorsqu’un appareil revient en ligne, tous les accès stockés sur l’appareil sont envoyés aux serveurs de collecte de données Adobe. Un grand nombre d’accès en file d’attente peut avoir un impact sur les performances des anciens appareils. Utilisez la variable `offlineThrottleDelay` pour déterminer la fréquence d’envoi des accès en file d’attente à Adobe.

## Délai de ralentissement hors ligne dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Launch pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.offlineThrottleDelay dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.offlineThrottleDelay` est un entier qui représente le nombre de millisecondes d’attente AppMeasurement entre l’envoi des accès en file d’attente. Sa valeur par défaut est `0`, ce qui signifie que tous les accès en file d’attente sont envoyés simultanément. Si `trackOffline` correspond à `false`, cette variable ne fait rien.

```js
s.offlineThrottleDelay = 500;
```
