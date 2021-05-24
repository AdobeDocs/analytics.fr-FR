---
title: trackExternalLinks
description: Permet d’activer ou de désactiver le suivi automatique des liens pour les liens de sortie.
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '185'
ht-degree: 100%

---

# trackExternalLinks

Adobe permet de suivre les liens sortants sans définir manuellement la méthode [`tl()`](../functions/tl-method.md) de chaque lien de sortie. Activez cette variable si vous souhaitez utiliser le suivi automatique des liens pour les liens de sortie.

Lorsqu’il est activé, AppMeasurement compare toute URL de lien sur lequel l’utilisateur a cliqué aux valeurs des sections [`linkInternalFilters`](linkinternalfilters.md) et [`linkExternalFilters`](linkexternalfilters.md). S’il existe une correspondance, un appel de suivi des liens de sortie se déclenche automatiquement.

## Suivi des liens sortants dans Adobe Experience Platform Launch

Le suivi des liens sortants est une case à cocher située sous l’accordéon [!UICONTROL Suivi des liens] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Suivi des liens], qui affiche la case à cocher [!UICONTROL Suivi des liens sortants].

Cochez la case pour activer le suivi automatique des liens de sortie.

## s.trackExternalLinks dans AppMeasurement et l’éditeur de code personnalisé de Launch

`s.trackExternalLinks` est une valeur booléenne qui active ou désactive le suivi automatique des liens de sortie. Si vous ne souhaitez pas suivre les liens sortants ou si vous préférez appeler manuellement la méthode `tl()` de suivi des liens de sortie, définissez cette variable sur `false`.

```js
s.trackExternalLinks = true;
```
