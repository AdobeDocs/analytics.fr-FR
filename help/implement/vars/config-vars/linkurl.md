---
title: linkURL
description: Permet de remplacer l’URL de lien générée automatiquement utilisée par AppMeasurement dans les appels de suivi des liens.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkURL

Chaque fois qu’un appel de suivi des liens est envoyé à Adobe, les serveurs de collecte de données détectent automatiquement l’URL. Utilisez la variable `linkURL` pour remplacer l’URL détectée.

## URL du lien dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Launch pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.linkURL dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.linkURL` est une chaîne contenant l’URL du navigateur lorsque l’utilisateur a cliqué sur le lien. Cette variable ne renseigne aucune dimension disponible dans les rapports.

```js
s.linkURL = "https://example.com";
```

Si la variable [`linkName`](linkname.md) n’est pas définie pour un appel de suivi de lien, la variable `linkURL` est utilisée à la place.
