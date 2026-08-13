---
title: offlineThrottleDelay
description: Permet de définir la fréquence des accès lorsqu’un appareil revient en ligne.
feature: Appmeasurement Implementation
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/FiC4yXkRmNoY0PPO9ouC8-hX5xqWhkbcDVht5f05Yqk'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 195
ht-degree: 83%

---

# offlineThrottleDelay

Le suivi hors ligne est une méthode facultative de collecte de données dans Adobe Analytics. Si un visiteur se déconnecte d’Internet mais continue à parcourir votre site, les accès sont stockés dans une file d’attente hors ligne jusqu’à ce que l’appareil se reconnecte à Internet. Le suivi hors ligne est principalement utilisé pour les applications mobiles.

Lorsqu’un appareil revient en ligne, tous les accès stockés sur l’appareil sont envoyés aux serveurs de collecte de données Adobe. Un grand nombre d’accès en file d’attente peut avoir un impact sur les performances des anciens appareils. Utilisez la variable `offlineThrottleDelay` pour déterminer la fréquence d’envoi des accès en file d’attente à Adobe.

## Délai de ralentissement hors ligne à l’aide de Web SDK

Le SDK Web ne prend pas en charge le suivi hors ligne.

## Délai de ralentissement hors ligne à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.offlineThrottleDelay dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.offlineThrottleDelay` est un entier qui représente le nombre de millisecondes d’attente AppMeasurement entre l’envoi des accès en file d’attente. Sa valeur par défaut est `0`, ce qui signifie que tous les accès en file d’attente sont envoyés simultanément. Si `trackOffline` correspond à `false`, cette variable ne fait rien.

```js
s.offlineThrottleDelay = 500;
```
