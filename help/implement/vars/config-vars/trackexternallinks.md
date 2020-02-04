---
title: trackExternalLinks
description: Activez ou désactivez le suivi automatique des liens pour les liens de sortie.
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# trackExternalLinks

Adobe permet de suivre les liens sortants sans définir manuellement la `tl()` fonction de chaque lien de sortie. Activez cette variable si vous souhaitez utiliser le suivi automatique des liens pour les liens de sortie.

Lorsqu’il est activé, AppMeasurement compare toute URL de lien sur lequel l’utilisateur a cliqué aux valeurs des sections `linkInternalFilters` et `linkExternalFilters`. S’il existe une correspondance, un appel de suivi des liens de sortie se déclenche automatiquement.

## Suivi des liens sortants dans le lancement d’Adobe Experience Platform

Le suivi des liens sortants est une case à cocher située sous l’accordéon Suivi des [!UICONTROL liens] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon Suivi des [!UICONTROL liens] , qui affiche la case à cocher [!UICONTROL Suivi des liens] sortants.

Cochez la case pour activer le suivi automatique des liens de sortie.

## s.trackExternalLinks dans AppMeasurement et lancement de l’éditeur de code personnalisé

Il `s.trackExternalLinks` s’agit d’une valeur booléenne qui active ou désactive le suivi automatique des liens de sortie. Si vous ne souhaitez pas suivre les liens sortants ou si vous préférez appeler manuellement la `tl()` fonction pour suivre les liens de sortie, définissez cette variable sur `false`.

```js
s.trackDownloadLinks = true;
```
