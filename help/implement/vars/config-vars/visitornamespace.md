---
title: visitorNameSpace
description: Variable retraitée qui a déterminé le domaine du cookie.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# visitorNamespace

> [!IMPORTANT] Cette variable est retirée. Utilisez [`trackingServer`](trackingserver.md) plutôt.

Dans les versions précédentes d’Adobe Analytics, AppMeasurement utilisait la `visitorNameSpace` variable pour déterminer le sous-domaine de `2o7.net` l’emplacement de stockage des cookies de. L’augmentation des pratiques de confidentialité dans les navigateurs modernes rend les cookies tiers moins fiables. Avec l&#39;introduction des `trackingServer` et [`trackingServerSecure`](trackingserversecure.md) variables, `visitorNameSpace` n&#39;est plus nécessaire.

> [!TIP] Adobe recommande d’utiliser des cookies propriétaires sur votre site. Les cookies propriétaires n’utilisent pas cette variable.

##   dans Adobe Experience Platform Launch

[!UICONTROL Visitor Namespace] est un champ sous l’ [!UICONTROL Cookies] accordéon lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Configure] bouton sous Adobe Analytics.
4. Développez l’ [!UICONTROL Cookies] accordéon, ce qui révèle le [!UICONTROL Visitor Namespace] champ.

Adobe recommande de ne pas utiliser ce champ. Utilisez `trackingServer` et `trackingServerSecure` à la place.

## s.visitorNamespace dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.visitorNamespace` variable est une chaîne qui contient une valeur unique par organisation. Les anciennes bibliothèques AppMeasurement incluaient automatiquement cette valeur unique lorsqu’elles étaient téléchargées à partir des versions précédentes d’Adobe Analytics. Les bibliothèques AppMeasurement actuelles n’utilisent pas cette variable, sauf si `trackingServer` et `trackingServerSecure` ne sont pas définies.

Si votre organisation a toujours besoin de cette variable, sélectionnez une valeur qui représente votre organisation. Vous pouvez stocker cette valeur dans un de conception de [solution](../../prepare/solution-design.md).

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
