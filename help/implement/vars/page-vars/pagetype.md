---
title: pageType
description: Permet de déterminer si la page active est une erreur 404.
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 77%

---

# pageType

La variable `pageType` est un indicateur utilisé pour désigner les pages d’erreur de votre site, telles que les erreurs 404. Si cette variable contient la chaîne `errorPage`, elle renseigne la dimension Pages introuvables.

>[!IMPORTANT]
>
>Ne définissez pas cette variable sur les pages sans erreur.

## Type de page à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.pageType dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.pageType` est une chaîne dont la valeur `errorPage` est la seule valeur valide. Définissez cette variable sur cette valeur dans toute page d’erreur de votre site, par exemple sur des pages 404.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Utilisez une eVar pour collecter le code d’erreur afin d’obtenir plus d’informations sur les erreurs spécifiques rencontrées par les visiteurs sur votre site.
