---
title: trackExternalLinks
description: Permet d’activer ou de désactiver le suivi automatique des liens pour les liens de sortie.
feature: Variables
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 60%

---

# trackExternalLinks

Adobe permet de suivre les liens sortants sans définir manuellement la méthode [`tl()`](../functions/tl-method.md) de chaque lien de sortie. Activez cette variable si vous souhaitez utiliser le suivi automatique des liens pour les liens de sortie.

Lorsqu’il est activé, AppMeasurement compare toute URL de lien sur lequel l’utilisateur a cliqué aux valeurs des sections [`linkInternalFilters`](linkinternalfilters.md) et [`linkExternalFilters`](linkexternalfilters.md). S’il existe une correspondance, un appel de suivi des liens de sortie se déclenche automatiquement.

## Activation ou désactivation de la collecte de clics à l’aide de l’extension SDK Web

Cochez la case [!UICONTROL Activer la collecte de données de clic] lors de la configuration du SDK Web. Cette case à cocher gère les liens de sortie et de téléchargement.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton **[!UICONTROL Configurer]** sous [!UICONTROL SDK Web Adobe Experience Platform].
1. Sous [!UICONTROL Collecte de données], cochez la case **[!UICONTROL Activer la collecte de données de clic]** .

## Activer ou désactiver la collecte des clics en implémentant manuellement le SDK Web

Configurez le SDK à l’aide de [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=fr#clickCollectionEnabled). Le champ est une valeur booléenne qui détermine si les données associées aux clics sur les liens sont automatiquement collectées. Sa valeur par défaut est `true`. Définissez cette valeur sur `false` si vous souhaitez désactiver le suivi automatique des liens. Ce paramètre gère le suivi automatique des liens pour les liens de téléchargement et de sortie.

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
