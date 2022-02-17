---
title: trackDownloadLinks
description: Permet d’activer ou de désactiver le suivi automatique des liens pour les liens de téléchargement.
feature: Variables
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 100%

---

# trackDownLoadLinks

Adobe offre la possibilité de suivre les liens de téléchargement sans définir manuellement la méthode [`tl()`](../functions/tl-method.md) de chaque lien de téléchargement. Activez cette variable si vous souhaitez utiliser le suivi automatique des liens pour les liens de téléchargement.

Lorsqu’il est activé, AppMeasurement compare l’URL du lien sur lequel l’utilisateur a cliqué aux valeurs de [`linkDownloadFileTypes`](linkdownloadfiletypes.md). S’il existe une correspondance, un appel de suivi des liens de téléchargement se déclenche automatiquement.

## Suivi des liens de téléchargement à l’aide de balises dans Adobe Experience Platform

Lors de la configuration de l’extension Adobe Analytics, une case à cocher se trouve sous l’accordéon [!UICONTROL Suivi des liens] de téléchargement.

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Suivi des liens], qui affiche la case à cocher des [!UICONTROL liens de téléchargement de suivi].

Cochez la case pour activer le suivi automatique des liens de téléchargement.

## s.trackDownloadLinks dans AppMeasurement et l’éditeur de code personnalisé

`s.trackDownloadLinks` est d’une valeur booléenne qui active ou désactive le suivi automatique des liens de téléchargement. Si vous ne souhaitez pas suivre les liens de téléchargement ou si vous préférez appeler manuellement la méthode `tl()` pour effectuer le suivi des téléchargements, définissez cette variable sur `false`.

```js
s.trackDownloadLinks = true;
```
