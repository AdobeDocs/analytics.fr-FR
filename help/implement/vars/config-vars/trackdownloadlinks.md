---
title: trackDownloadLinks
description: Permet d’activer ou de désactiver le suivi automatique des liens pour les liens de téléchargement.
feature: Appmeasurement Implementation
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
role: Admin, Developer
source-git-commit: 7176e068dd05c5589d741f3194d2ad5d795e017d
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 50%

---

# trackDownloadLinks

Adobe offre la possibilité de suivre les liens de téléchargement sans définir manuellement la méthode [`tl()`](../functions/tl-method.md) de chaque lien de téléchargement. Activez cette variable si vous souhaitez utiliser le suivi automatique des liens pour les liens de téléchargement.

Lorsqu’il est activé, AppMeasurement compare l’URL du lien sur lequel l’utilisateur a cliqué aux valeurs de [`linkDownloadFileTypes`](linkdownloadfiletypes.md). S’il existe une correspondance, un appel de suivi des liens de téléchargement se déclenche automatiquement.

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

## Suivi des liens de téléchargement à l’aide de l’extension Adobe Analytics

Lors de la configuration de l’extension Adobe Analytics, une case à cocher se trouve sous l’accordéon [!UICONTROL Suivi des liens] de téléchargement.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Suivi des liens], qui affiche la case à cocher des [!UICONTROL liens de téléchargement de suivi].

Cochez la case pour activer le suivi automatique des liens de téléchargement.

## s.trackDownloadLinks dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

`s.trackDownloadLinks` est d’une valeur booléenne qui active ou désactive le suivi automatique des liens de téléchargement. Si vous ne souhaitez pas effectuer le suivi des liens de téléchargement ou si vous préférez appeler manuellement la méthode `tl()` pour effectuer le suivi des téléchargements, définissez cette variable sur `false`. La variable [linkDownloadFileTypes](linkdownloadfiletypes.md) doit également être définie pour que le suivi automatique des liens de téléchargement fonctionne.

```js
s.trackDownloadLinks = true;
```
