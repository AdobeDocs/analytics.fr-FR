---
title: fpcookieDomainPeriods
description: Permet d’aider AppMeasurement à comprendre quel domaine doit conserver les cookies si votre domaine comporte un point dans son suffixe.
feature: Appmeasurement Implementation
exl-id: e994a188-1dab-4bf0-912b-cd2f6a1032e0
role: Admin, Developer
TQID: https://experienceleague.adobe.com/c8ynLzlV-tctlh1Aw2TRBfgiLbwlP4cLB-UfrFFsgTU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 296
ht-degree: 86%

---

# fpCookieDomainPeriods

La variable `fpCookieDomainPeriods` permet à AppMeasurement de déterminer où les cookies Analytics sont définis en précisant que le suffixe de domaine comporte un point supplémentaire. Cette variable permet à AppMeasurement de prendre en compte le point supplémentaire dans le suffixe du domaine et de définir les cookies au bon emplacement. Il hérite de la valeur de [`cookieDomainPeriods`](cookiedomainperiods.md), mais il est toujours recommandé de définir si vous utilisez une mise en œuvre de cookies propriétaires.

* Pour les domaines tels que `example.com` ou `www.example.com`, cette variable n’a pas besoin d’être définie. Si nécessaire, vous pouvez définir cette variable sur `"2"`.
* Pour les domaines tels que `example.co.uk` ou `www.example.co.jp`, définissez cette variable sur `"3"`.

>[!IMPORTANT]
>
>Ne prenez pas en compte les sous-domaines pour cette variable. Par exemple, ne définissez pas `fpCookieDomainPeriods` l’URL `store.toys.example.com`. AppMeasurement reconnaît par défaut que les cookies doivent être conservés sur `example.com`, même sur les URL comportant de nombreux sous-domaines.

## Périodes de domaine propriétaires à l’aide de Web SDK

Web SDK peut déterminer le domaine de stockage des cookies approprié sans cette variable.

## Points de domaine propriétaires à l’aide de l’extension Adobe Analytics

Les périodes de domaine propriétaires sont un champ sous l’accordéon [!UICONTROL Cookies] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Cookies], qui affiche le champ [!UICONTROL Périodes de domaine de premier niveau].

Définissez ce champ sur `3` uniquement pour les domaines contenant un point dans le suffixe. Sinon, ce champ peut être laissé vide.

## s.fpCookieDomainPeriods dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `fpCookieDomainPeriods` est une chaîne généralement définie sur `"3"`, uniquement pour les domaines qui contiennent un point dans le suffixe. Sa valeur par défaut est `"2"`, ce qui prend en charge la plupart des domaines.

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
