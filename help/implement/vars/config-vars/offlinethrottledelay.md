---
title: offlineThrottleDelay
description: Définit la fréquence des accès lorsqu’un périphérique revient en ligne.
translation-type: tm+mt
source-git-commit: f313fd0c9ffda054a18ad1d457a74602b08e51fa

---


# offlineThrottleDelay

Le suivi hors ligne est une méthode facultative de collecte de données dans Adobe Analytics. Si un visiteur se déconnecte d’Internet mais continue à parcourir votre site, les accès sont stockés dans une file d’attente hors ligne jusqu’à ce que le périphérique se reconnecte à Internet. Le suivi hors ligne est principalement utilisé pour les applications mobiles.

Lorsqu’un périphérique revient en ligne, tous les accès stockés sur le périphérique sont envoyés aux serveurs de collecte de données Adobe. Un grand nombre d’accès en file d’attente peut avoir un impact sur les performances des anciens périphériques. Utilisez la `offlineThrottleDelay` variable pour déterminer la fréquence d’envoi des accès en file d’attente à Adobe.

## Délai de ralentissement hors ligne dans le lancement d’Adobe Experience Platform

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.offlineThrottleDelay dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.offlineThrottleDelay` variable est un entier qui représente le nombre de millisecondes d’attente AppMeasurement entre l’envoi des accès en file d’attente. Sa valeur par défaut est `0`, ce qui signifie que tous les accès en file d’attente sont envoyés simultanément. Si `trackOffline` est `false`, cette variable ne fait rien.

```js
s.offlineThrottleDelay = 500;
```
