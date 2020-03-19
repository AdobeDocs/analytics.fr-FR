---
title: usePlugins
description: Activez ou désactivez la fonction doPlugins().
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# usePlugins

Si `usePlugins` est activée, la [`doPlugins()`](../functions/doplugins.md) fonction s’exécute juste avant la compilation d’AppMeasurement et l’envoi d’un accès à Adobe. Activez cette variable si vous utilisez la `doPlugins()` fonction.

## Utilisation des modules externes dans le lancement d’Adobe Experience Platform

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.usePlugins dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.usePlugins` variable est une valeur booléenne qui détermine si AppMeasurement appelle la `doPlugins()` fonction. Its default value is `false`. Définissez cette variable sur `true` si vous utilisez la `doPlugins()` fonction dans votre implémentation.

```js
s.usePlugins = true;
```
