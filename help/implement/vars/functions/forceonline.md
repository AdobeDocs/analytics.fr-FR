---
title: forceOnline
description: Permet de définir manuellement l’état en ligne d’AppMeasurement.
feature: Appmeasurement Implementation
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/qPSlGDmNTccOtGRvlu-xr-wf1hV18OA-yyiuScnZr7g'
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
source-wordcount: 157
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

## Forcer la mise en ligne à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.forceOnline() dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Vous pouvez appeler la méthode `s.forceOnline()` n’importe où dans votre mise en œuvre après avoir appelé l’objet Analytics.

```js
s.forceOnline();
```
