---
title: pageType
description: Permet de déterminer si la page active est une erreur 404.
feature: Appmeasurement Implementation
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
TQID: https://experienceleague.adobe.com/SD-hwWJmZby-y99FIZHrnevSBsVqD6T5gwovn5tJfxo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 202
ht-degree: 75%

---

# pageType

La variable `pageType` est un indicateur utilisé pour désigner les pages d’erreur de votre site, telles que les erreurs 404. Si cette variable contient la chaîne `errorPage`, elle renseigne la [dimension](/help/components/dimensions/pages-not-found.md) et la [mesure](/help/components/metrics/pages-not-found.md) « Pages introuvables ».

>[!IMPORTANT]
>
>Ne définissez pas cette variable sur les pages sans erreur.

## Type de page utilisant le SDK Web

Le canal est mappé aux variables suivantes :

* [Objet XDM](/help/implement/aep-edge/xdm-var-mapping.md) : `xdm.web.webPageDetails.isErrorPage` - ce champ XDM est un booléen ; définissez-le sur `true` pour le signaler comme une page d’erreur, ou `false` s’il ne s’agit pas d’une page d’erreur.
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
