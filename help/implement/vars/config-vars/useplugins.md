---
title: usePlugins
description: Permet d’activer ou de désactiver la fonction doPlugins().
feature: Appmeasurement Implementation
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/7ofbF5EloAUlvCmGv-CaTFxxZELX0wydJ8HzmU2f6EQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 32%

---

# usePlugins

Si `usePlugins` est activée, la fonction [`doPlugins()`](../functions/doplugins.md) s’exécute juste avant la compilation d’AppMeasurement et l’envoi d’un accès à Adobe. Activez cette variable si vous utilisez la fonction `doPlugins()`.

## Utiliser le rappel `onBeforeEventSend` à l’aide de Web SDK

Bien que le SDK Web ne dispose pas d’une valeur booléenne pour gérer l’exécution d’une logique supplémentaire avant l’envoi des données à Adobe, vous pouvez enregistrer le rappel `onBeforeEventSend` pour modifier les données. Voir [Modifier globalement les événements](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) dans la documentation de Web SDK pour plus d’informations.

## Utilisation de plug-ins à l’aide de l’extension Adobe Analytics

Adobe fournit une extension appelée « Plug-ins Analytics courants » qui vous permet d’appeler la plupart des [Plug-ins](../plugins/impl-plugins.md). Installez l’extension et appelez le plug-in souhaité dans une règle.

Si le module externe souhaité n’est pas inclus dans l’extension Adobe, utilisez l’éditeur de code personnalisé en respectant la syntaxe AppMeasurement.

## s.usePlugins dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.usePlugins` est une valeur booléenne qui détermine si AppMeasurement appelle la fonction `doPlugins()`. Sa valeur par défaut est `false`. Définissez cette variable sur `true` si vous utilisez la fonction `doPlugins()` dans votre mise en œuvre.

```js
s.usePlugins = true;
```
