---
title: visitorNameSpace
description: Variable retraitée qui a déterminé le domaine du cookie.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# visitorNamespace

> [!IMPORTANT] Cette variable est retirée. Utilisez `trackingServer` plutôt.

Dans les versions précédentes d’Adobe Analytics, AppMeasurement utilisait la `visitorNameSpace` variable pour déterminer le sous-domaine de `2o7.net` l’emplacement de stockage des cookies de visiteurs. L’augmentation des pratiques de confidentialité dans les navigateurs modernes rend les cookies tiers moins fiables. Avec l&#39;introduction des `trackingServer` et `trackingServerSecure` variables, `visitorNameSpace` n&#39;est plus nécessaire.

> [!TIP] Adobe recommande d’utiliser des cookies propriétaires sur votre site. Les cookies propriétaires n’utilisent pas cette variable.

## Espace de nom du visiteur dans Adobe Experience Platform Launch

[!UICONTROL L’espace de nom] du visiteur est un champ situé sous l’accordéon [!UICONTROL Cookies] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Cookies] , qui affiche le champ Espace de nom du [!UICONTROL visiteur] .

Adobe recommande de ne pas utiliser ce champ. Utilisez `trackingServer` et `trackingServerSecure` à la place.

## s.visitorNamespace dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.visitorNamespace` variable est une chaîne qui contient une valeur unique par organisation. Les anciennes bibliothèques AppMeasurement incluaient automatiquement cette valeur unique lorsqu’elles étaient téléchargées à partir des versions précédentes d’Adobe Analytics. Les bibliothèques AppMeasurement actuelles n’utilisent pas cette variable, sauf si `trackingServer` et `trackingServerSecure` ne sont pas définies.

Si votre organisation a toujours besoin de cette variable, sélectionnez une valeur qui représente votre organisation. Vous pouvez stocker cette valeur dans un document [de conception de](../../prepare/solution-design.md)solution.

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
