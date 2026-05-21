---
title: trackExternalLinks
description: Permet d’activer ou de désactiver le suivi automatique des liens pour les liens de sortie.
feature: Appmeasurement Implementation
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
role: Admin, Developer
TQID: https://experienceleague.adobe.com/jNToCI8XjnbDNdTj6gwveVIWt3Ehue6Hp1HWM789UeI
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
source-wordcount: 340
ht-degree: 59%

---

# trackExternalLinks

Adobe permet de suivre les liens sortants sans définir manuellement la méthode [`tl()`](../functions/tl-method.md) de chaque lien de sortie. Activez cette variable si vous souhaitez utiliser le suivi automatique des liens pour les liens de sortie.

Lorsqu’il est activé, AppMeasurement compare toute URL de lien sur lequel l’utilisateur a cliqué aux valeurs des sections [`linkInternalFilters`](linkinternalfilters.md) et [`linkExternalFilters`](linkexternalfilters.md). S’il existe une correspondance, un appel de suivi des liens de sortie se déclenche automatiquement.

## Activer ou désactiver la collecte de clics à l’aide de l’extension Web SDK

Utilisez la case à cocher [!UICONTROL Activer la collecte de données de clics] lors de la configuration de Web SDK. Cette case à cocher gère les liens de sortie et de téléchargement.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous [!UICONTROL Adobe Experience Platform Web SDK].
1. Sous [!UICONTROL Collecte de données], cochez la case **[!UICONTROL Activer la collecte de données]**.

## Activer ou désactiver la collecte de clics implémentant manuellement le SDK Web

Configurez le SDK à l’aide de [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled). Le champ est une valeur booléenne qui détermine si les données associées aux clics sur les liens sont automatiquement collectées. Sa valeur par défaut est `true`. Définissez cette valeur sur `false` si vous souhaitez désactiver le suivi automatique des liens. Ce paramètre gère le suivi automatique des liens de téléchargement et de sortie.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Suivi des liens sortants à l’aide de l’extension Adobe Analytics

Le suivi des liens sortants est une case à cocher située sous l’accordéon [!UICONTROL Suivi des liens] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Suivi des liens], qui affiche la case à cocher [!UICONTROL Suivi des liens sortants].

Cochez la case pour activer le suivi automatique des liens de sortie.

## s.trackExternalLinks dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

`s.trackExternalLinks` est une valeur booléenne qui active ou désactive le suivi automatique des liens de sortie. Si vous ne souhaitez pas suivre les liens sortants ou si vous préférez appeler manuellement la méthode `tl()` de suivi des liens de sortie, définissez cette variable sur `false`.

```js
s.trackExternalLinks = true;
```
