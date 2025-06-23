---
title: usePlugins
description: Permet d’activer ou de désactiver la fonction doPlugins().
feature: Appmeasurement Implementation
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 34%

---

# usePlugins

Si `usePlugins` est activée, la fonction [`doPlugins()`](../functions/doplugins.md) s’exécute juste avant la compilation d’AppMeasurement et l’envoi d’un accès à Adobe. Activez cette variable si vous utilisez la fonction `doPlugins()`.

## Utiliser le rappel `onBeforeEventSend` à l’aide de Web SDK

Bien que le SDK Web ne dispose pas d’une valeur booléenne pour gérer l’exécution d’une logique supplémentaire avant l’envoi des données à Adobe, vous pouvez enregistrer le rappel `onBeforeEventSend` pour modifier les données. Voir [Modifier globalement les événements](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=fr#modifying-events-globally) dans la documentation de Web SDK pour plus d’informations.

## Utilisation de plug-ins à l’aide de l’extension Adobe Analytics

Adobe fournit une extension appelée « Plug-ins Analytics courants » qui vous permet d’appeler la plupart des [Plug-ins](../plugins/impl-plugins.md). Installez l’extension et appelez le plug-in souhaité dans une règle.

Si le module externe souhaité n’est pas inclus dans l’extension Adobe, utilisez l’éditeur de code personnalisé en respectant la syntaxe AppMeasurement.

## s.usePlugins dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.usePlugins` est une valeur booléenne qui détermine si AppMeasurement appelle la fonction `doPlugins()`. Sa valeur par défaut est `false`. Définissez cette variable sur `true` si vous utilisez la fonction `doPlugins()` dans votre mise en œuvre.

```js
s.usePlugins = true;
```
