---
title: offlineHitLimit
description: Déterminez le nombre maximal d’accès à mettre en file d’attente pour le suivi hors ligne.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# offlineHitLimit

Le suivi hors ligne est une méthode facultative de collecte de données dans Adobe Analytics. Si un se déconnecte d’Internet mais continue à parcourir votre site, les accès sont stockés dans une file d’attente hors ligne jusqu’à ce que le périphérique se reconnecte à Internet. Le suivi hors ligne est principalement utilisé pour les applications mobiles.

La `offlineHitLimit` variable plafonne le nombre d’accès que le périphérique stocke localement. Cette variable ne fonctionne que si [`trackOffline`](trackoffline.md) elle est activée.

## Limite d’accès hors ligne dans le lancement d’Adobe Experience Platform

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.offlineHitLimit dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.offlineHitLimit` variable est un entier représentant le nombre maximal d’accès qu’un périphérique stocke lorsqu’il est hors ligne. Si cette variable n’est pas définie, le nombre d’accès qu’un périphérique stocke hors ligne n’est pas limité.

```js
s.offlineHitLimit = 100;
```
