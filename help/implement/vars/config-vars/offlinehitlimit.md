---
title: offlineHitLimit
description: Permet de déterminer le nombre maximal d’accès à mettre en file d’attente pour le suivi hors ligne.
feature: Appmeasurement Implementation
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 39%

---

# offlineHitLimit

Le suivi hors ligne est une méthode facultative de collecte de données dans Adobe Analytics. Si un visiteur se déconnecte d’Internet mais continue à parcourir votre site, les accès sont stockés dans une file d’attente hors ligne jusqu’à ce que l’appareil se reconnecte à Internet. Le suivi hors ligne est principalement utilisé pour les applications mobiles.

La variable `offlineHitLimit` limite le nombre d’accès que l’appareil stocke localement. Cette variable ne fonctionne que si [`trackOffline`](trackoffline.md) est activé.

## Limite d’accès hors ligne à l’aide de Web SDK

Le SDK Web ne prend pas en charge le suivi hors ligne.

## Limite d’accès hors ligne à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.offlineHitLimit dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.offlineHitLimit` est un entier représentant le nombre maximal d’accès qu’un appareil stocke lorsqu’il est hors ligne. Si cette variable n’est pas définie, elle est définie par défaut sur `10`. Vous pouvez le définir sur n’importe quelle valeur entière. Lorsque vous définissez des valeurs élevées, tenez compte des limites de stockage locales dans le navigateur d’un visiteur. Cette limite est généralement comprise entre 5 et 10 Mo.

```js
s.offlineHitLimit = 100;
```
