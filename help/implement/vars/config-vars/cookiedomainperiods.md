---
title: cookieDomainPeriods
description: (Obsolète) Permet à l’AppMeasurement de déterminer où stocker les cookies lorsqu’un domaine de niveau supérieur d’un site web contient un point.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 19%

---


# cookieDomainPeriods

>[!IMPORTANT]
>Cette variable est obsolète. Si vous utilisez AppMeasurement v2.26.x ou version ultérieure, ou l’extension Adobe Analytics v1.9.4 ou version ultérieure, la bibliothèque détecte automatiquement le domaine sur lequel définir les cookies.

La variable `cookieDomainPeriods` a aidé l’AppMeasurement à déterminer où définir les cookies Analytics en indiquant que le domaine de niveau supérieur comportait un point supplémentaire. Cette variable a permis à AppMeasurement de prendre en compte le délai supplémentaire dans le domaine de niveau supérieur et de définir les cookies au bon emplacement. Si le domaine de niveau supérieur de votre site web ne comprend pas de période supplémentaire, cette variable n’est pas requise.

* Pour les domaines tels que `example.co.uk` ou `www.example.co.jp`, définissez cette variable sur `"3"`.
* Pour les domaines tels que `example.nsw.gov.au`, définissez cette variable sur `"4"`.
* Pour les domaines tels que `example.com` ou `products.example.org`, omettez de définir cette variable ou définissez-la sur `"2"`.

>[!TIP]
>
>Ne prenez pas en compte les sous-domaines pour cette variable. Par exemple, ne définissez pas `cookieDomainPeriods` l’URL `store.toys.example.com`. AppMeasurement reconnaît que les cookies sont stockés sur `example.com`, même sur les URL comportant de nombreux sous-domaines.

Pour les mises en oeuvre sur AppMeasurement v2.26.x ou version ultérieure, la variable [`s_ac`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) est utilisé pour aider à déterminer automatiquement le domaine de cookie correct. La bibliothèque tente d’écrire un cookie comprenant deux points de domaine. Si la définition de ce cookie échoue, il effectue une nouvelle tentative, y compris d’autres points de domaine jusqu’à ce qu’il réussisse. Une fois défini, ce cookie est immédiatement supprimé.

## Cookie des périodes de domaine à l’aide du SDK Web

Le SDK Web détermine automatiquement le domaine correct pour définir les cookies.

## Cookie des périodes de domaine à l’aide de l’extension Adobe Analytics

**[!UICONTROL Nombre de points du domaine]** est un champ situé sous la propriété [!UICONTROL Cookies] en accordéon lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Cookies], qui affiche le champ [!UICONTROL Points de domaine].

Définissez ce champ sur `3` uniquement sur les domaines de niveau supérieur contenant un point. Sinon, ce champ peut être laissé vide.

## Périodes de domaine de cookie dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `cookieDomainPeriods` est une chaîne généralement définie sur `"3"`, uniquement sur les domaines de niveau supérieur contenant un point. Sa valeur par défaut est `"2"`, qui prend en charge la plupart des domaines de niveau supérieur tels que `.com` et `.org`.

```js
// Manually set cookieDomainPeriods for domains with a period in the top-level domain, such as www.example.co.uk
s.cookieDomainPeriods = "3";
```
