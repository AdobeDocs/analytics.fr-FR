---
title: Résolution de l’écran
description: Résolution en pixels de l’écran du visiteur.
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
TQID: https://experienceleague.adobe.com/d3AuMT0seRbZpuKVGPeWo98Bkhc8tcJIP6gt4y-rq38
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 51%
---
# Résolution de l’écran

La [dimension](overview.md) « Résolution du moniteur » indique la hauteur et la largeur de l’affichage actif en pixels. Cette dimension est utile pour savoir où se trouve le « pli » de votre site pour les visiteurs ou pour connaître la largeur de la fenêtre de leur navigateur. Identifier l’emplacement du pli peut vous permettre d’optimiser l’affichage du contenu.

Cette dimension est différente de la [hauteur](browser-height.md) et de la [largeur](browser-width.md) du navigateur. La hauteur/largeur du navigateur correspond au nombre de pixels dans l’espace du navigateur consultable, tandis que la résolution de l’écran correspond au nombre de pixels de l’ensemble de l’écran. Si vous souhaitez voir la différence entre ces deux variables sur votre propre ordinateur, ouvrez la console du navigateur (F12 sur la plupart des navigateurs) et effectuez un copier-coller du code suivant dans la console :

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "; Browser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Les dimensions du navigateur sont toujours plus petites que la résolution de l’écran, car les dimensions du navigateur n’incluent ni la navigation ni les bordures du navigateur.

## Renseignement de cette dimension avec des données

La résolution du moniteur est collectée automatiquement, côté client, à partir des propriétés `screen.width` et `screen.height` du navigateur. Elle est prête à l’emploi dans toute implémentation d’AppMeasurement ou de Web SDK (balises). Il n’y a aucune variable à définir. Si vous collectez des données en dehors d’AppMeasurement ou de Web SDK (par exemple via l’API), envoyez la valeur dans les demandes d’image. S’il est manquant ou si une bibliothèque de collecte de données ne peut pas collecter la résolution du moniteur, ces données sont répertoriées sous [!UICONTROL `Not Specified`].

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (collecté automatiquement) |
| **Champ Web SDK/XDM** | Aucun (collecté automatiquement) |
| **Paramètre de requête** | [`s`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<resolution>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | 20 octets |
| **Persistance** | S.O. |

## Éléments de dimension

Les éléments de dimension incluent toutes les résolutions d’écran collectées. Les exemples de valeurs comprennent `1920 x 1080`, `1366 x 768` et `1280 x 720`.
