---
title: cookieDomain
description: (Retiré) Permet de déterminer le domaine sur lequel définir les cookies.
feature: Appmeasurement Implementation
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
role: Admin, Developer
TQID: https://experienceleague.adobe.com/z6occeGLpxezOj7go2DrwG-j-fc9yBuGyHSmZJK9RfQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 198
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

## Domaine de cookie utilisant le SDK Web

Web SDK peut déterminer le domaine de stockage des cookies approprié sans cette variable.

## Domaine de cookie utilisant l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.cookieDomain dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `cookieDomain` est une chaîne qui est définie sur le domaine sur lequel vous souhaitez conserver les cookies.

```js
s.cookieDomain = "stats.example.com";
```
