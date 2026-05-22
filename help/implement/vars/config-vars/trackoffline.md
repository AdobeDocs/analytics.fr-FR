---
title: trackOffline
description: Permet d’activer ou de désactiver le suivi hors ligne, qui modifie la manière dont AppMeasurement collecte les données.
feature: Appmeasurement Implementation
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/6VDAO0-QMXqia2Ddy1uPcxnTrlJi49B8zjaLcC0HawU'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 283
ht-degree: 89%

---

# trackOffline

Le suivi hors ligne est une méthode facultative de collecte de données dans Adobe Analytics. Si un visiteur se déconnecte d’Internet mais continue à parcourir votre site, les accès sont stockés dans une file d’attente hors ligne jusqu’à ce que l’appareil se reconnecte à Internet. Le suivi hors ligne est principalement utilisé pour les applications mobiles.

La variable `trackOffline` détermine si vous souhaitez utiliser le suivi hors ligne dans votre mise en œuvre.

>[!WARNING]
>
>Vous devez configurer votre suite de rapports pour accepter les accès horodatés avant d’activer cette variable. Si une suite de rapports n’accepte pas les accès horodatés et que cette variable est activée, ces données sont perdues et ne peuvent pas être récupérées.

Lorsqu’il est activé, AppMeasurement utilise le processus suivant pour envoyer des données à Adobe :

* Lors de la compilation d’une demande d’image, un paramètre de chaîne de requête d’horodatage est inclus.
* Si l’appareil ne parvient pas à atteindre les serveurs de collecte de données Adobe, l’accès est stocké localement sur l’appareil.
* Lors de chaque accès suivant, AppMeasurement tente d’envoyer une demande d’image à Adobe.
   * S’il ne parvient pas à atteindre les serveurs de collecte de données Adobe, l’accès est ajouté à la file d’attente sur l’appareil.
   * S’il peut atteindre les serveurs de collecte de données Adobe, l’accès et la file d’attente des accès lorsque l’appareil était hors ligne sont envoyés.

## Tracking hors ligne à l’aide de Web SDK

Le SDK Web ne prend pas en charge le suivi hors ligne.

## Suivi hors ligne à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.trackOffline dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.trackOffline` est une valeur booléenne qui active ou désactive le suivi hors ligne. Sa valeur par défaut est `false`. Définissez cette valeur sur `true` si vous souhaitez activer le suivi hors ligne.

```js
s.trackOffline = true;
```
