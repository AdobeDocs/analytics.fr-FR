---
title: useBeacon
description: useBeacon vous permet de forcer AppMeasurement à utiliser l’API sendBeacon des navigateurs
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# useBeacon

La plupart des navigateurs modernes incluent la méthode native `navigator.sendBeacon()`. Elle envoie de manière asynchrone une petite quantité de données via HTTP à un serveur Web. AppMeasurement peut utiliser la `navigator.sendBeacon()` méthode si la `useBeacon` variable est activée. Il est utile pour les liens de sortie et les autres situations où vous souhaitez envoyer des informations avant le déchargement de la page.

Si `useBeacon` est activé, l’accès suivant envoyé à Adobe utilise la `navigator.sendBeacon()` méthode du navigateur au lieu d’une demande d’ `GET` image standard. Cette variable s’applique aux demandes d’image [`s.t()`](../functions/t-method.md) et [`s.tl()`](../functions/tl-method.md) aux demandes d’image. Il nécessite AppMeasurement 2.17.0 ou une version ultérieure.

> [!TIP] AppMeasurement active automatiquement `useBeacon` les demandes d’image de lien de sortie.

La `useBeacon` variable est ignorée lorsque le utilise un navigateur qui ne prend pas en charge `navigator.sendBeacon()`. L’utilisation de cette variable nécessite AppMeasurement 2.16.0 ou version ultérieure.

## Utiliser la balise dans le lancement d’Adobe Experience Platform

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.useBeacon dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.useBeacon` variable est une valeur booléenne qui détermine si AppMeasurement utilise la `navigator.sendBeacon()` méthode du navigateur. Its default value is `false`. Définissez cette variable sur `true` avant d’appeler une fonction de suivi si vous souhaitez utiliser la nature asynchrone de `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

> [!NOTE] Après l’exécution d’un appel de suivi, cette variable est réinitialisée sur `false`. Si votre implémentation envoie plusieurs demandes d’image au même chargement de page (comme les applications d’une seule page), définissez cette variable sur `true` avant chaque appel de suivi.
