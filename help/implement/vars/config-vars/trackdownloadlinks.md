---
title: trackDownloadLinks
description: Permet d’activer ou de désactiver le suivi automatique des liens pour les liens de téléchargement.
translation-type: ht
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackDownLoadLinks

Adobe offre la possibilité de suivre les liens de téléchargement sans définir manuellement la méthode [`tl()`](../functions/tl-method.md) de chaque lien de téléchargement. Activez cette variable si vous souhaitez utiliser le suivi automatique des liens pour les liens de téléchargement.

Lorsqu’il est activé, AppMeasurement compare l’URL du lien sur lequel l’utilisateur a cliqué aux valeurs de [`linkDownloadFileTypes`](linkdownloadfiletypes.md). S’il existe une correspondance, un appel de suivi des liens de téléchargement se déclenche automatiquement.

## Suivi des liens de téléchargement dans Adobe Experience Platform Launch

Lors de la configuration de l’extension Adobe Analytics, une case à cocher se trouve sous l’accordéon [!UICONTROL Suivi des liens] de téléchargement.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Suivi des liens], qui affiche la case à cocher des [!UICONTROL liens de téléchargement de suivi].

Cochez la case pour activer le suivi automatique des liens de téléchargement.

## s.trackDownloadLinks dans AppMeasurement et l’éditeur de code personnalisé de Launch

`s.trackDownloadLinks` est d’une valeur booléenne qui active ou désactive le suivi automatique des liens de téléchargement. Si vous ne souhaitez pas suivre les liens de téléchargement ou si vous préférez appeler manuellement la méthode `tl()` pour effectuer le suivi des téléchargements, définissez cette variable sur `false`.

```js
s.trackDownloadLinks = true;
```
