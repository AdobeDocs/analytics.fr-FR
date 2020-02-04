---
title: cookieDomain
description: La variable cookieDomain permet de déterminer le domaine sur lequel les cookies doivent être définis.
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# cookieDomain

> [!IMPORTANT] Cette variable est retirée. Utilisez `trackingServer` plutôt.

La `cookieDomain` variable détermine le domaine dans lequel AppMeasurement définit les cookies. Vous pouvez utiliser cette variable pour définir explicitement le domaine du cookie au lieu d’utiliser la `cookieDomainPeriods` variable.

Cette variable ne doit être utilisée que lorsque **les deux** conditions suivantes sont remplies :

* Si votre implémentation utilise des cookies propriétaires. Cette variable n’est pas requise avec les implémentations utilisant une `trackingServer` valeur contenant `sc.omtrdc.net`.
* Si votre domaine comporte un point dans son suffixe. Par exemple, `example.co.uk` vous pouvez utiliser la `cookieDomain` variable pour indiquer explicitement que le domaine du cookie est `example.co.uk` et non `co.uk`.

Seul un petit nombre d’implémentations ont été utilisées pour la `cookieDomain` variable. D’autres variables, telles que `cookieDomainPeriods` peuvent être utilisées à la place.

## Domaine du cookie dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.cookieDomain dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `cookieDomain` variable est une chaîne et est définie sur le domaine sur lequel vous souhaitez stocker les cookies.

```js
s.cookieDomain = "stats.example.com";
```
