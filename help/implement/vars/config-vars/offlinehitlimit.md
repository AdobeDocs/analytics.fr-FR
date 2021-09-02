---
title: offlineHitLimit
description: Permet de déterminer le nombre maximal d’accès à mettre en file d’attente pour le suivi hors ligne.
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '158'
ht-degree: 100%

---

# offlineHitLimit

Le suivi hors ligne est une méthode facultative de collecte de données dans Adobe Analytics. Si un visiteur se déconnecte d’Internet mais continue à parcourir votre site, les accès sont stockés dans une file d’attente hors ligne jusqu’à ce que l’appareil se reconnecte à Internet. Le suivi hors ligne est principalement utilisé pour les applications mobiles.

La variable `offlineHitLimit` plafonne le nombre d’accès que l’appareil stocke localement. Cette variable ne fonctionne que si [`trackOffline`](trackoffline.md) est activé.

## Limite d’accès hors ligne à l’aide de balises dans Adobe Experience Platform

Il n’existe pas de champ dédié dans l’interface utilisateur de la collecte de données pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.offlineHitLimit dans AppMeasurement et l’éditeur de code personnalisé

La variable `s.offlineHitLimit` est un entier représentant le nombre maximal d’accès qu’un appareil stocke lorsqu’il est hors ligne. Si cette variable n’est pas définie, le nombre d’accès qu’un appareil stocke hors ligne n’est pas limité.

```js
s.offlineHitLimit = 100;
```
