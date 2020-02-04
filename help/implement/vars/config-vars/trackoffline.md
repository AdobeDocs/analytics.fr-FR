---
title: trackOffline
description: Activez ou désactivez le suivi hors ligne, qui modifie la manière dont AppMeasurement collecte les données.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackOffline

Le suivi hors ligne est une méthode facultative de collecte de données dans Adobe Analytics. Si un visiteur se déconnecte d’Internet mais continue à parcourir votre site, les accès sont stockés dans une file d’attente hors ligne jusqu’à ce que le périphérique se reconnecte à Internet. Le suivi hors ligne est principalement utilisé pour les applications mobiles.

La `trackOffline` variable détermine si vous souhaitez utiliser le suivi hors ligne dans votre implémentation.

> [!IMPORTANT] Vous devez configurer votre suite de rapports pour accepter les accès horodatés avant d’activer cette variable. Si une suite de rapports n’accepte pas les accès horodatés et que cette variable est activée, ces données sont perdues et ne peuvent pas être récupérées.

Lorsqu’il est activé, AppMeasurement utilise le processus suivant pour envoyer des données à Adobe :

* Lors de la compilation d’une demande d’image, un paramètre de chaîne de requête d’horodatage est inclus.
* Si le périphérique ne parvient pas à atteindre les serveurs de collecte de données Adobe, l’accès est stocké localement sur le périphérique.
* Lors de chaque accès suivant, AppMeasurement tente d’envoyer une demande d’image à Adobe.
   * S’il ne parvient pas à atteindre les serveurs de collecte de données Adobe, l’accès est ajouté à la file d’attente sur le périphérique.
   * S’il peut atteindre les serveurs de collecte de données Adobe, l’accès et la file d’attente des accès lorsque le périphérique était hors ligne sont envoyés.

## Suivi hors ligne dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.trackOffline dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.trackOffline` variable est une valeur booléenne qui active ou désactive le suivi hors ligne. Its default value is `false`. Définissez cette valeur sur `true` si vous souhaitez activer le suivi hors ligne.

```js
s.trackOffline = true;
```
