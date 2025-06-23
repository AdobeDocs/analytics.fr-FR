---
title: trackOffline
description: Permet d’activer ou de désactiver le suivi hors ligne, qui modifie la manière dont AppMeasurement collecte les données.
feature: Appmeasurement Implementation
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '283'
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
