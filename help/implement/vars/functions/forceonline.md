---
title: forceOnline
description: Permet de définir manuellement l’état en ligne d’AppMeasurement.
feature: Variables
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 80%

---

# forceOnline

La méthode `forceOnline()` vous permet de remplacer l’état d’AppMeasurement détecté automatiquement.

>[!WARNING]
>
>N’utilisez cette fonction que lorsque [`trackOffline`](../config-vars/trackoffline.md) est activé. L’utilisation de cette fonction en dehors du suivi hors ligne peut entraîner une perte de données.

AppMeasurement détecte automatiquement l’état en ligne de l’appareil. Vous pouvez utiliser la méthode `forceOnline()` pour forcer AppMeasurement à traiter les accès comme si l’appareil était en ligne. Cette méthode ne prend aucun argument et ne renvoie aucune valeur. Son seul objectif est de remplacer l’état en ligne dans AppMeasurement.

## Forcer la mise en ligne à l’aide du SDK Web

Le SDK Web ne prend pas en charge le suivi hors ligne.

## Forcer l’utilisation de l’extension Adobe Analytics en ligne

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.forceOnline() dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Vous pouvez appeler la méthode `s.forceOnline()` n’importe où dans votre mise en œuvre après avoir appelé l’objet Analytics.

```js
s.forceOnline();
```
