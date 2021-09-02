---
title: usePlugins
description: Permet d’activer ou de désactiver la fonction doPlugins().
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '98'
ht-degree: 100%

---

# usePlugins

Si `usePlugins` est activée, la fonction [`doPlugins()`](../functions/doplugins.md) s’exécute juste avant la compilation d’AppMeasurement et l’envoi d’un accès à Adobe. Activez cette variable si vous utilisez la fonction `doPlugins()`.

## Utilisation de plug-ins à l’aide de balises dans Adobe Experience Platform

Il n’existe pas de champ dédié dans l’interface utilisateur de la collecte de données pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.usePlugins dans AppMeasurement et l’éditeur de code personnalisé

La variable `s.usePlugins` est une valeur booléenne qui détermine si AppMeasurement appelle la fonction `doPlugins()`. Sa valeur par défaut est `false`. Définissez cette variable sur `true` si vous utilisez la fonction `doPlugins()` dans votre mise en œuvre.

```js
s.usePlugins = true;
```
