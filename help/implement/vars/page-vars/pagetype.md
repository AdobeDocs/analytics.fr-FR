---
title: pageType
description: Permet de déterminer si la page active est une erreur 404.
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 100%

---

# pageType

La variable `pageType` est un indicateur utilisé pour désigner les pages d’erreur de votre site, telles que les erreurs 404. Si cette variable contient la chaîne `errorPage`, elle renseigne la dimension Pages introuvables.

>[!IMPORTANT]
>
>Ne définissez pas cette variable sur les pages sans erreur.

## Type de page à l’aide de balises dans Adobe Experience Platform

Il n’existe pas de champ dédié dans l’interface utilisateur de la collecte de données pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.pageType dans AppMeasurement et l’éditeur de code personnalisé

La variable `s.pageType` est une chaîne dont la valeur `errorPage` est la seule valeur valide. Définissez cette variable sur cette valeur dans toute page d’erreur de votre site, par exemple sur des pages 404.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Utilisez une eVar pour collecter le code d’erreur afin d’obtenir plus d’informations sur les erreurs spécifiques rencontrées par les visiteurs sur votre site.
