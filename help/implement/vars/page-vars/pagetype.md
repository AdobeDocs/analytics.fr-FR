---
title: pageType
description: Permet de déterminer si la page active est une erreur 404.
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 100%

---

# pageType

La variable `pageType` est un indicateur utilisé pour désigner les pages d’erreur de votre site, telles que les erreurs 404. Si cette variable contient la chaîne `errorPage`, elle renseigne la [dimension](/help/components/dimensions/pages-not-found.md) et la [mesure](/help/components/metrics/pages-not-found.md) « Pages introuvables ».

>[!IMPORTANT]
>
>Ne définissez pas cette variable sur les pages sans erreur.

## Type de page utilisant le SDK Web

Le type de page est [mappé pour Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=fr) sous le champ XDM `web.webPageDetails.isErrorPage`. Ce champ XDM est un booléen ; définissez-le sur `true` pour le signaler comme une page d’erreur, ou `false` s’il ne s’agit pas d’une page d’erreur. Adobe convertit automatiquement le booléen en valeur de chaîne `errorPage` lorsqu’il est envoyé à une suite de rapports Analytic.

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
