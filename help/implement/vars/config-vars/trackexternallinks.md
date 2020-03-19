---
title: trackExternalLinks
description: Activez ou désactivez le suivi automatique des liens pour les liens de sortie.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackExternalLinks

Adobe  la possibilité de suivre les liens sortants  sans définir manuellement la [`tl()`](../functions/tl-method.md) méthode pour chaque lien de sortie. Activez cette variable si vous souhaitez utiliser le suivi automatique des liens pour les liens de sortie.

Lorsqu’il est activé, AppMeasurement compare toute URL de lien sur lequel l’utilisateur a cliqué aux valeurs des sections [`linkInternalFilters`](linkinternalfilters.md) et [`linkExternalFilters`](linkexternalfilters.md). S’il existe une correspondance, un appel de suivi des liens de sortie se déclenche automatiquement.

## Suivi des liens sortants dans le lancement d’Adobe Experience Platform

Le suivi des liens sortants est une case à cocher située sous l’ [!UICONTROL Link Tracking] accordéon lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Configure] bouton sous Adobe Analytics.
4. Développez l’ [!UICONTROL Link Tracking] accordéon, qui affiche la [!UICONTROL Track outbound links] case à cocher.

Cochez la case pour activer le suivi automatique des liens de sortie.

## s.trackExternalLinks dans AppMeasurement et lancement de l’éditeur de code personnalisé

Il `s.trackExternalLinks` s’agit d’une valeur booléenne qui active ou désactive le suivi automatique des liens de sortie. Si vous ne souhaitez pas suivre les liens sortants ou si vous préférez appeler manuellement la `tl()` méthode pour suivre les liens de sortie, définissez cette variable sur `false`.

```js
s.trackDownloadLinks = true;
```
