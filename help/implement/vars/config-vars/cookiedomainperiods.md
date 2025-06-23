---
title: cookieDomainPeriods
description: (Obsolète) Aidez AppMeasurement à déterminer où stocker les cookies lorsque le domaine de niveau supérieur d’un site web contient un point.
feature: Appmeasurement Implementation
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 18%

---

# cookieDomainPeriods

>[!IMPORTANT]
>Cette variable est obsolète. Si vous utilisez l’un des médicaments suivants :
>
>* AppMeasurement v2.26.x ou version ultérieure
>* Extension Adobe Analytics v1.9.4 ou version ultérieure
>* Service Adobe Experience Cloud ID
>
>Cette variable n’a aucun effet, car la bibliothèque applicable détecte automatiquement le domaine sur lequel définir les cookies.

La variable `cookieDomainPeriods` a aidé AppMeasurement à déterminer où définir les cookies Analytics en indiquant que le domaine de niveau supérieur y avait une période supplémentaire. Cette variable permettait à AppMeasurement d’accommoder la période supplémentaire dans le domaine de niveau supérieur et de définir les cookies à l’emplacement correct. Si le domaine de niveau supérieur de votre site web n’inclut pas de période supplémentaire, cette variable n’est pas obligatoire.

* Pour les domaines tels que `example.co.uk` ou `www.example.co.jp`, définissez cette variable sur `"3"`.
* Pour des domaines tels que `example.nsw.gov.au`, définissez cette variable sur `"4"`.
* Pour les domaines tels que `example.com` ou `products.example.org`, omettez de définir cette variable ou définissez-la sur `"2"`.

>[!TIP]
>
>Ne prenez pas en compte les sous-domaines pour cette variable. Par exemple, ne définissez pas `cookieDomainPeriods` l’URL `store.toys.example.com`. AppMeasurement reconnaît que les cookies sont stockés sur des `example.com`, même sur des URL comportant de nombreux sous-domaines.

Pour les implémentations sur AppMeasurement v2.26.x ou version ultérieure, le cookie [`s_ac`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) est utilisé pour aider à déterminer automatiquement le domaine de cookie correct. La bibliothèque tente d’abord d’écrire un cookie comprenant deux périodes de domaine. Si la définition de ce cookie échoue, il réessaye, y compris d’autres périodes de domaine jusqu’à ce qu’il réussisse. Ce cookie est immédiatement supprimé une fois défini.

## Période des domaines de cookie à l’aide de Web SDK

Web SDK détermine automatiquement le domaine approprié pour définir les cookies.

## Points des domaines de cookie utilisant l’extension Adobe Analytics

**[!UICONTROL Points de domaine]** est un champ sous l’accordéon [!UICONTROL Cookies] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Cookies], qui affiche le champ [!UICONTROL Points de domaine].

Définissez ce champ sur `3` uniquement sur les domaines de niveau supérieur contenant un point. Dans le cas contraire, ce champ peut rester vide.

## Points de domaine de cookie dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `cookieDomainPeriods` est une chaîne généralement définie sur `"3"`, uniquement sur les domaines de niveau supérieur contenant un point. Sa valeur par défaut est `"2"`, qui prend en charge la plupart des domaines de niveau supérieur tels que `.com` et `.org`.

```js
// Manually set cookieDomainPeriods for domains with a period in the top-level domain, such as www.example.co.uk
s.cookieDomainPeriods = "3";
```
