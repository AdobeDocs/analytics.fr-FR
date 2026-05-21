---
title: visitorNameSpace
description: (Supprimé) Aide à déterminer le domaine de cookies tiers.
feature: Appmeasurement Implementation
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
role: Admin, Developer
TQID: https://experienceleague.adobe.com/y9oXzSzgN-s8gVrdHs0nFRm0ASSbUPzlkW-V6u1GnMg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 226
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

[!UICONTROL L’espace de noms du visiteur] est un champ situé sous l’accordéon [!UICONTROL Cookies] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Cookies], qui affiche le champ [!UICONTROL Espace de noms du visiteur].

Adobe recommande de ne pas utiliser ce champ. Utilisez `trackingServer` et `trackingServerSecure` à la place.

## s.visitorNamespace dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.visitorNamespace` est une chaîne qui contient une valeur unique par organisation. Les anciennes bibliothèques AppMeasurement incluaient automatiquement cette valeur unique lorsqu’elles étaient téléchargées à partir des versions précédentes d’Adobe Analytics. Les bibliothèques AppMeasurement actuelles n’utilisent pas cette variable, sauf si `trackingServer` et `trackingServerSecure` ne sont pas définies.

Si votre organisation a toujours besoin de cette variable, sélectionnez une valeur qui représente votre organisation. Vous pouvez stocker cette valeur dans un [document de conception de solution](../../prepare/solution-design.md).

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
