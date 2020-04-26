---
title: trackExternalLinks
description: Permet d’activer ou de désactiver le suivi automatique des liens pour les liens de sortie.
translation-type: tm+mt
source-git-commit: 94218548dc4e3efd57df95c992003e94640e4330

---


# trackExternalLinks

Adobe offers the ability to track outbound links without manually setting the [`tl()`](../functions/tl-method.md) method for each exit link. Activez cette variable si vous souhaitez utiliser le suivi automatique des liens pour les liens de sortie.

Lorsqu’il est activé, AppMeasurement compare toute URL de lien sur lequel l’utilisateur a cliqué aux valeurs des sections [`linkInternalFilters`](linkinternalfilters.md) et [`linkExternalFilters`](linkexternalfilters.md). S’il existe une correspondance, un appel de suivi des liens de sortie se déclenche automatiquement.

## Suivi des liens sortants dans Adobe Experience Platform Launch

Le suivi des liens sortants est une case à cocher située sous l’accordéon [!UICONTROL Suivi des liens] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Suivi des liens], qui affiche la case à cocher [!UICONTROL Suivi des liens sortants].

Cochez la case pour activer le suivi automatique des liens de sortie.

## s.trackExternalLinks dans AppMeasurement et l’éditeur de code personnalisé de Launch

`s.trackExternalLinks` est une valeur booléenne qui active ou désactive le suivi automatique des liens de sortie. If you do not want to track outbound links, or would prefer to manually call the `tl()` method to track exit links, set this variable to `false`.

```js
s.trackExternalLinks = true;
```
