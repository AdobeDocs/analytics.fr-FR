---
title: forceOffline
description: Permet de définir manuellement l’état en ligne d’AppMeasurement.
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '138'
ht-degree: 100%

---

# forceOffline

La méthode `forceOffline()` vous permet de remplacer l’état d’AppMeasurement détecté automatiquement.

>[!IMPORTANT]
>
>N’utilisez cette fonction que lorsque [`trackOffline`](../config-vars/trackoffline.md) est activé. L’utilisation de cette fonction en dehors du suivi hors ligne peut entraîner une perte de données.

AppMeasurement détecte automatiquement l’état en ligne de l’appareil. Vous pouvez utiliser la méthode `forceOffline()` pour forcer AppMeasurement à traiter les accès comme si l’appareil était hors ligne. Cette méthode ne prend aucun argument et ne renvoie aucune valeur. Son seul objectif est de remplacer l’état en ligne dans AppMeasurement.

## Forcer l’état hors ligne dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Launch pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.forceOffline() dans AppMeasurement et l’éditeur de code personnalisé de Launch

Vous pouvez appeler la méthode `s.forceOffline()` n’importe où dans votre mise en œuvre après avoir appelé l’objet Analytics.

```js
s.forceOffline();
```
