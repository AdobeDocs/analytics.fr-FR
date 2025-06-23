---
title: visitorNameSpace
description: (Supprimé) Aide à déterminer le domaine de cookies tiers.
feature: Appmeasurement Implementation
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 89%

---

# visitorNamespace

>[!IMPORTANT]
>
>Cette variable a été abandonnée. Utilisez [`trackingServer`](trackingserver.md) à la place.

Dans les versions précédentes d’Adobe Analytics, AppMeasurement utilisait la variable `visitorNameSpace` pour déterminer le sous-domaine de `2o7.net`, l’emplacement de stockage des cookies de visiteurs. L’augmentation des pratiques de confidentialité dans les navigateurs modernes rend les cookies tiers moins fiables. Avec l’introduction des variables `trackingServer` et [`trackingServerSecure`](trackingserversecure.md), `visitorNameSpace` n’est plus nécessaire.

>[!TIP]
>
>Adobe recommande d’utiliser des cookies propriétaires sur votre site. Les cookies propriétaires n’utilisent pas cette variable.

## Espace de noms du visiteur utilisant l’extension Adobe Analytics

[!UICONTROL L’espace de nom du visiteur] est un champ situé sous l’accordéon [!UICONTROL Cookies] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Cookies], qui affiche le champ [!UICONTROL Espace de nom du visiteur].

Adobe recommande de ne pas utiliser ce champ. Utilisez `trackingServer` et `trackingServerSecure` à la place.

## s.visitorNamespace dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.visitorNamespace` est une chaîne qui contient une valeur unique par organisation. Les anciennes bibliothèques AppMeasurement incluaient automatiquement cette valeur unique lorsqu’elles étaient téléchargées à partir des versions précédentes d’Adobe Analytics. Les bibliothèques AppMeasurement actuelles n’utilisent pas cette variable, sauf si `trackingServer` et `trackingServerSecure` ne sont pas définies.

Si votre organisation a toujours besoin de cette variable, sélectionnez une valeur qui représente votre organisation. Vous pouvez stocker cette valeur dans un [document de conception de solution](../../prepare/solution-design.md).

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
