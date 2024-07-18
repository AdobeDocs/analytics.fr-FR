---
title: pageType
description: Permet de déterminer si la page active est une erreur 404.
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 75%

---

# pageType

La variable `pageType` est un indicateur utilisé pour désigner les pages d’erreur de votre site, telles que les erreurs 404. Si cette variable contient la chaîne `errorPage`, elle renseigne la [dimension](/help/components/dimensions/pages-not-found.md) et la [mesure](/help/components/metrics/pages-not-found.md) « Pages introuvables ».

>[!IMPORTANT]
>
>Ne définissez pas cette variable sur les pages sans erreur.

## Type de page utilisant le SDK Web

Le canal est mappé aux variables suivantes :

* [Objet XDM](/help/implement/aep-edge/xdm-var-mapping.md) : `xdm.web.webPageDetails.isErrorPage` - ce champ XDM est une valeur booléenne ; définissez-le sur `true` pour le signaler comme une page d’erreur ou `false` s’il ne s’agit pas d’une page d’erreur.
* [Objet de données](/help/implement/aep-edge/data-var-mapping.md) : `data.__adobe.analytics.pageType` - ce champ d’objet de données est une chaîne ; définissez-le sur `"errorPage"` pour le marquer comme tel.

## Type de page utilisant l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.pageType dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.pageType` est une chaîne dont la valeur `errorPage` est la seule valeur valide. Définissez cette variable sur cette valeur dans toute page d’erreur de votre site, par exemple sur des pages 404.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Utilisez une eVar pour collecter le code d’erreur afin d’obtenir plus d’informations sur les erreurs spécifiques rencontrées par les visiteurs sur votre site.
