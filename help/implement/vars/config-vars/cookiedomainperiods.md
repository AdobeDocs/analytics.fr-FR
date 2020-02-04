---
title: cookieDomainPeriods
description: Aidez AppMeasurement à comprendre quel domaine stocker les cookies si votre domaine comporte un point dans son suffixe.
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# cookieDomainPeriods

AppMeasurement détermine son emplacement de cookie en examinant le suffixe de domaine et de domaine. Pour les domaines tels `example.com`que, AppMeasurement définit les cookies à l’emplacement correct. Toutefois, pour d’autres domaines, comme `example.co.uk`AppMeasurement peut par erreur définir des cookies sur `co.uk`. La plupart des navigateurs rejettent les cookies définis sur ce domaine non valide, ce qui entraîne des problèmes d’identification des visiteurs.

La `cookieDomainPeriods` variable permet à AppMeasurement de déterminer où les cookies Analytics sont définis en appelant que le suffixe de domaine comporte une période supplémentaire. Cette variable permet à AppMeasurement de prendre en compte la période supplémentaire dans le suffixe du domaine et de définir les cookies au bon emplacement.

* Pour les domaines tels `example.com` ou `www.example.com`, cette variable n’a pas besoin d’être définie. Si nécessaire, vous pouvez définir cette variable sur `"2"`.
* Pour les domaines comme `example.co.uk` ou `www.example.co.jp`, définissez cette variable sur `"3"`.

> [!IMPORTANT] Ne prenez pas en compte les sous-domaines pour cette variable. Par exemple, ne définissez pas `cookieDomainPeriods` l’URL `store.toys.example.com`. AppMeasurement reconnaît par défaut que les cookies doivent être stockés sur `example.com`, même sur les URL comportant de nombreux sous-domaines.

## Périodes de domaine dans Adobe Experience Platform Launch

Les périodes de domaine sont un champ sous l’accordéon [!UICONTROL Cookies] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Cookies] , qui affiche le champ Périodes [!UICONTROL de] domaine.

Définissez ce champ sur `3` uniquement les domaines contenant un point dans son suffixe. Sinon, ce champ peut être laissé vide.

## s.cookieDomainPeriods dans AppMeasurement et le lancement de l’éditeur de code personnalisé

La `cookieDomainPeriods` variable est une chaîne généralement définie sur `"3"`, uniquement sur les domaines qui contiennent un point dans son suffixe. Sa valeur par défaut est `"2"`, ce qui prend en charge la plupart des domaines.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
