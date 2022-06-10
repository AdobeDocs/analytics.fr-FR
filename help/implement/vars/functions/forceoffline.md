---
title: forceOffline
description: Permet de définir manuellement l’état en ligne d’AppMeasurement.
feature: Variables
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 70%

---

# forceOffline

La méthode `forceOffline()` vous permet de remplacer l’état d’AppMeasurement détecté automatiquement.

>[!WARNING]
>
>N’utilisez cette fonction que lorsque [`trackOffline`](../config-vars/trackoffline.md) est activé. L’utilisation de cette fonction en dehors du suivi hors ligne peut entraîner une perte de données.

AppMeasurement détecte automatiquement l’état en ligne de l’appareil. Vous pouvez utiliser la méthode `forceOffline()` pour forcer AppMeasurement à traiter les accès comme si l’appareil était hors ligne. Cette méthode ne prend aucun argument et ne renvoie aucune valeur. Son seul objectif est de remplacer l’état en ligne dans AppMeasurement.

## Forcer la mise hors ligne à l’aide du SDK Web

Le SDK Web ne prend pas en charge le suivi hors ligne.

## Forcer la mise hors ligne à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.forceOffline() dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Vous pouvez appeler la méthode `s.forceOffline()` n’importe où dans votre mise en œuvre après avoir appelé l’objet Analytics.

```js
s.forceOffline();
```
