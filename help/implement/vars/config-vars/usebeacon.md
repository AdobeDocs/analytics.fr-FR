---
title: useBeacon
description: useBeacon vous permet de forcer AppMeasurement à utiliser l’API sendBeacon des navigateurs
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '229'
ht-degree: 100%

---

# useBeacon

La plupart des navigateurs modernes incluent la méthode native `navigator.sendBeacon()`. Elle envoie de manière asynchrone une petite quantité de données via HTTP à un serveur web. AppMeasurement peut utiliser la méthode `navigator.sendBeacon()` si la variable `useBeacon` est activée. Il est utile pour les liens de sortie et les autres situations où vous souhaitez envoyer des informations avant le déchargement de la page.

Si `useBeacon` est activé, l’accès suivant envoyé à Adobe utilise la méthode `navigator.sendBeacon()` du navigateur au lieu d’une demande d’image `GET` standard. Cette variable s’applique aux demandes d’image [`s.t()`](../functions/t-method.md) et aux demandes d’image [`s.tl()`](../functions/tl-method.md). Elle nécessite AppMeasurement 2.17.0 ou une version ultérieure.

>[!TIP]
>
> AppMeasurement active automatiquement les demandes d’image de lien de sortie `useBeacon`.

La variable `useBeacon` est ignorée lorsque le visiteur utilise un navigateur qui ne prend pas en charge `navigator.sendBeacon()`. L’utilisation de cette variable nécessite AppMeasurement 2.16.0 ou une version ultérieure.

## Utilisation de la balise dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Launch pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.useBeacon dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.useBeacon` est une valeur booléenne qui détermine si AppMeasurement utilise la méthode `navigator.sendBeacon()` du navigateur. Sa valeur par défaut est `false`. Définissez cette variable sur `true` avant d’appeler une fonction de suivi si vous souhaitez utiliser la nature asynchrone de `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>Après l’exécution d’un appel de suivi, cette variable est réinitialisée sur `false`. Si votre mise en œuvre envoie plusieurs demandes d’image au même chargement de page (comme les applications d’une seule page), définissez cette variable sur `true` avant chaque appel de suivi.
