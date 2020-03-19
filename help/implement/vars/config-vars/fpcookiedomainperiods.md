---
title: cookieDomainPeriods
description: Aidez AppMeasurement à comprendre quel domaine stocker les cookies si votre domaine comporte un point dans son suffixe.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# fpCookieDomainPeriods

La `fpCookieDomainPeriods` variable permet à AppMeasurement de déterminer où les cookies Analytics sont définis en appelant que le suffixe de domaine comporte une période supplémentaire. Cette variable permet à AppMeasurement de prendre en compte la période supplémentaire dans le suffixe du domaine et de définir les cookies au bon emplacement. Il hérite de la valeur de [`cookieDomainPeriods`](cookiedomainperiods.md), mais reste une bonne pratique à définir si vous utilisez une implémentation de cookies propriétaires.

* Pour les domaines tels `example.com` ou `www.example.com`, cette variable n’a pas besoin d’être définie. Si nécessaire, vous pouvez définir cette variable sur `"2"`.
* Pour les domaines comme `example.co.uk` ou `www.example.co.jp`, définissez cette variable sur `"3"`.

> [!IMPORTANT] Ne prenez pas en compte les sous-domaines pour cette variable. Par exemple, ne définissez pas `fpCookieDomainPeriods` l’URL `store.toys.example.com`. AppMeasurement reconnaît par défaut que les cookies doivent être stockés sur `example.com`, même sur les URL comportant de nombreux sous-domaines.

## Périodes de domaine propriétaires dans Adobe Experience Platform Launch

Les périodes de domaine propriétaires sont un champ sous l’ [!UICONTROL Cookies] accordéon lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Configure] bouton sous Adobe Analytics.
4. Développez l’ [!UICONTROL Cookies] accordéon, ce qui révèle le [!UICONTROL First-party Domain Periods] champ.

Définissez ce champ sur `3` uniquement les domaines contenant un point dans son suffixe. Sinon, ce champ peut être laissé vide.

## s.fpCookieDomainPeriods dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `fpCookieDomainPeriods` variable est une chaîne généralement définie sur `"3"`, uniquement sur les domaines qui contiennent un point dans son suffixe. Sa valeur par défaut est `"2"`, ce qui prend en charge la plupart des domaines.

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
