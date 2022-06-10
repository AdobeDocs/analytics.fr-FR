---
title: usePlugins
description: Permet d’activer ou de désactiver la fonction doPlugins().
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 43%

---

# usePlugins

Si `usePlugins` est activée, la fonction [`doPlugins()`](../functions/doplugins.md) s’exécute juste avant la compilation d’AppMeasurement et l’envoi d’un accès à Adobe. Activez cette variable si vous utilisez la fonction `doPlugins()`.

## Utilisez la variable `onBeforeEventSend` rappel à l’aide du SDK Web

Bien que le SDK Web ne dispose pas d’une valeur booléenne pour gérer l’exécution d’une logique supplémentaire avant que les données ne soient envoyées à Adobe, vous pouvez enregistrer la variable `onBeforeEventSend` rappel pour modifier des données. Voir [Modification globale des événements](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) pour plus d’informations, voir la documentation du SDK Web .

## Utilisation de plug-ins à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.usePlugins dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.usePlugins` est une valeur booléenne qui détermine si AppMeasurement appelle la fonction `doPlugins()`. Sa valeur par défaut est `false`. Définissez cette variable sur `true` si vous utilisez la fonction `doPlugins()` dans votre mise en œuvre.

```js
s.usePlugins = true;
```
