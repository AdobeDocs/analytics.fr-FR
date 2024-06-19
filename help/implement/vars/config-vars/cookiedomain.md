---
title: cookieDomain
description: (Retiré) Permet de déterminer le domaine sur lequel les cookies doivent être définis.
feature: Variables
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 77%

---

# cookieDomain

>[!IMPORTANT]
>Cette variable a été abandonnée. Utilisez [`trackingServer`](trackingserver.md) à la place.

La variable `cookieDomain` détermine le domaine dans lequel AppMeasurement définit les cookies. Vous pouvez utiliser cette variable pour définir explicitement le domaine du cookie au lieu d’utiliser la variable [`cookieDomainPeriods`](cookiedomainperiods.md).

Cette variable ne doit être utilisée que lorsque **les deux** conditions suivantes sont réunies :

* Votre mise en œuvre utilise des cookies propriétaires. Cette variable n’est pas requise avec les mises en œuvre utilisant une valeur [`trackingServer`](trackingserver.md) contenant `sc.adobedc.net`.
* Votre domaine comporte un point dans son suffixe. Par exemple, `example.co.uk` peut utiliser la variable `cookieDomain` pour indiquer explicitement que le domaine du cookie est `example.co.uk` et non `co.uk`.

Seul un petit nombre de mises en œuvre ont été utilisées pour la variable `cookieDomain`. D’autres variables, telles que [`cookieDomainPeriods`](cookiedomainperiods.md), peuvent être utilisées à la place.

## Domaine du cookie à l’aide du SDK Web

Le SDK Web peut déterminer le domaine de stockage de cookies correct sans cette variable.

## Domaine du cookie à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.cookieDomain dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `cookieDomain` est une chaîne qui est définie sur le domaine sur lequel vous souhaitez conserver les cookies.

```js
s.cookieDomain = "stats.example.com";
```
