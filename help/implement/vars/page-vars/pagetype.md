---
title: pageType
description: Déterminez si la page active est une erreur 404.
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# pageType

La `pageType` variable est un indicateur utilisé pour désigner les pages d’erreur de votre site, telles que les erreurs 404. Si cette variable contient la chaîne `errorPage`, elle renseigne la dimension Pages introuvables.

> [!IMPORTANT] Ne définissez pas cette variable sur les pages sans erreur.

## Type de page dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.pageType dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.pageType` variable est une chaîne dont la valeur `errorPage` est sa seule valeur valide. Définissez cette variable sur cette valeur dans toute page d’erreur de votre site, par exemple sur 404 pages.

```js
s.pageType = "errorPage";
```

> [!TIP] Utilisez une eVar pour collecter le code d’erreur afin d’obtenir plus d’informations sur les erreurs spécifiques rencontrées par les visiteurs sur votre site.
