---
title: cookieDomain
description: La variable cookieDomain permet de déterminer le domaine sur lequel les cookies doivent être définis.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 100%

---


# cookieDomain

>[!IMPORTANT]
>
>Cette variable a été abandonnée. Utilisez [`trackingServer`](trackingserver.md) à la place.

La variable `cookieDomain` détermine le domaine dans lequel AppMeasurement définit les cookies. Vous pouvez utiliser cette variable pour définir explicitement le domaine du cookie au lieu d’utiliser la variable [`cookieDomainPeriods`](cookiedomainperiods.md).

Cette variable ne doit être utilisée que lorsque **les deux** conditions suivantes sont réunies :

* Votre mise en œuvre utilise des cookies propriétaires. Cette variable n’est pas requise avec les mises en œuvre utilisant une valeur [`trackingServer`](trackingserver.md) contenant `sc.omtrdc.net`.
* Votre domaine comporte un point dans son suffixe. Par exemple, `example.co.uk` peut utiliser la variable `cookieDomain` pour indiquer explicitement que le domaine du cookie est `example.co.uk` et non `co.uk`.

Seul un petit nombre de mises en œuvre ont été utilisées pour la variable `cookieDomain`. D’autres variables, telles que [`cookieDomainPeriods`](cookiedomainperiods.md), peuvent être utilisées à la place.

## Domaine du cookie dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Launch pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.cookieDomain dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `cookieDomain` est une chaîne qui est définie sur le domaine sur lequel vous souhaitez conserver les cookies.

```js
s.cookieDomain = "stats.example.com";
```
