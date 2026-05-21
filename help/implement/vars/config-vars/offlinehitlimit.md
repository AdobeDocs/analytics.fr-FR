---
title: offlineHitLimit
description: Permet de déterminer le nombre maximal d’accès à mettre en file d’attente pour le suivi hors ligne.
feature: Appmeasurement Implementation
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
TQID: https://experienceleague.adobe.com/-uvCAqUO0A-7XjlemN4XwHXVG9DFK-UoVTW77up9-AY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 194
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
