---
title: useBeacon
description: useBeacon vous permet de forcer AppMeasurement à utiliser l’API sendBeacon des navigateurs
keywords: Analytics Implementation
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.useBeacon

La `s.useBeacon` variable force la requête suivante à utiliser l’API [](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon)sendBeacon du navigateur. L’utilisation `s.sendBeacon` permet d’envoyer une requête HTTP en dehors du contexte d’une page. Il est utile pour les liens de sortie et les autres situations où vous souhaitez envoyer des informations avant le déchargement de la page.

La définition de cette valeur ne s’applique qu’à la requête suivante déclenchée par AppMeasurement. Une fois la requête déclenchée, `s.useBeacon` la valeur false est rétablie. Cette variable s’applique aux demandes d’image `s.t()` et `s.tl()` aux demandes d’image.

L’utilisation de la `s.useBeacon` variable nécessite AppMeasurement 2.17.0 ou une version ultérieure.

> [!NOTE] [ExitLinks](s-linktrackvars.md) utilise cette variable automatiquement sans configuration supplémentaire.

## du lien personnalisé

```js
s.useBeacon = true;
```
