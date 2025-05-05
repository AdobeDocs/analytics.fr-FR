---
title: usePlugins
description: Permet d’activer ou de désactiver la fonction doPlugins().
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 34%

---

# usePlugins

Si `usePlugins` est activée, la fonction [`doPlugins()`](../functions/doplugins.md) s’exécute juste avant la compilation d’AppMeasurement et l’envoi d’un accès à Adobe. Activez cette variable si vous utilisez la fonction `doPlugins()`.

## Utilisation du rappel `onBeforeEventSend` à l’aide du SDK Web

Bien que le SDK Web ne dispose pas d’une valeur booléenne pour gérer l’exécution d’une logique supplémentaire avant l’envoi des données à Adobe, vous pouvez enregistrer le rappel `onBeforeEventSend` pour modifier les données. Pour plus d’informations, voir [Modification des événements globalement](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=fr#modifying-events-globally) dans la documentation du SDK Web.

## Utilisation de plug-ins à l’aide de l’extension Adobe Analytics

Adobe fournit une extension appelée &quot;Plug-ins Analytics communs&quot; qui vous permet d’appeler la plupart des [plug-ins](../plugins/impl-plugins.md). Installez l’extension et appelez le plug-in souhaité dans une règle.

Si le module externe souhaité n’est pas inclus dans l’extension Adobe, utilisez l’éditeur de code personnalisé suivant la syntaxe de l’AppMeasurement.

## s.usePlugins dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.usePlugins` est une valeur booléenne qui détermine si AppMeasurement appelle la fonction `doPlugins()`. Sa valeur par défaut est `false`. Définissez cette variable sur `true` si vous utilisez la fonction `doPlugins()` dans votre mise en œuvre.

```js
s.usePlugins = true;
```
