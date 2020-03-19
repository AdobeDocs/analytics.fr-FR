---
title: trackDownloadLinks
description: Activez ou désactivez le suivi automatique des liens pour les liens de téléchargement.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackDownLoadLinks

Adobe  la possibilité de suivre  liens de téléchargement sans définir manuellement la [`tl()`](../functions/tl-method.md) méthode pour chaque lien de téléchargement. Activez cette variable si vous souhaitez utiliser le suivi automatique des liens pour les liens de téléchargement.

Lorsqu’il est activé, AppMeasurement compare l’URL du lien sur lequel l’utilisateur a cliqué aux valeurs de [`linkDownloadFileTypes`](linkdownloadfiletypes.md). S’il existe une correspondance, un appel de suivi des liens de téléchargement se déclenche automatiquement.

## Suivi des liens de téléchargement dans Adobe Experience Platform Launch

Les liens de téléchargement de suivi sont une case à cocher située sous l’ [!UICONTROL Link Tracking] accordéon lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Configure] bouton sous Adobe Analytics.
4. Développez l’ [!UICONTROL Link Tracking] accordéon, qui affiche la [!UICONTROL Track download links] case à cocher.

Cochez la case pour activer le suivi automatique des liens de téléchargement.

## s.trackDownloadLinks dans AppMeasurement et lancement de l’éditeur de code personnalisé

Il `s.trackDownloadLinks` s’agit d’une valeur booléenne qui active ou désactive le suivi automatique des liens de téléchargement. Si vous ne souhaitez pas suivre les liens de téléchargement ou si vous préférez appeler manuellement la `tl()` méthode pour effectuer le suivi des téléchargements, définissez cette variable sur `false`.

```js
s.trackDownloadLinks = true;
```
