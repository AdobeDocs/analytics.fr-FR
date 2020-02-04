---
title: trackDownloadLinks
description: Activez ou désactivez le suivi automatique des liens pour les liens de téléchargement.
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# trackDownLoadLinks

Adobe offre la possibilité de suivre les liens de téléchargement sans définir manuellement la `tl()` fonction de chaque lien de téléchargement. Activez cette variable si vous souhaitez utiliser le suivi automatique des liens pour les liens de téléchargement.

Lorsqu’il est activé, AppMeasurement compare l’URL du lien sur lequel l’utilisateur a cliqué aux valeurs de `downloadLinkFileTypes`. S’il existe une correspondance, un appel de suivi des liens de téléchargement se déclenche automatiquement.

## Suivi des liens de téléchargement dans Adobe Experience Platform Launch

Lors de la configuration de l’extension Adobe Analytics, une case à cocher se trouve sous l’accordéon Suivi des [!UICONTROL liens] de téléchargement.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon Suivi des [!UICONTROL liens] , qui affiche la case à cocher des liens [!UICONTROL de téléchargement de] suivi.

Cochez la case pour activer le suivi automatique des liens de téléchargement.

## s.trackDownloadLinks dans AppMeasurement et lancement de l’éditeur de code personnalisé

Il `s.trackDownloadLinks` s’agit d’une valeur booléenne qui active ou désactive le suivi automatique des liens de téléchargement. Si vous ne souhaitez pas suivre les liens de téléchargement ou si vous préférez appeler manuellement la `tl()` fonction pour effectuer le suivi des téléchargements, définissez cette variable sur `false`.

```js
s.trackDownloadLinks = true;
```
