---
title: Résolution de l’écran
description: Résolution en pixels de l’écran du visiteur.
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
source-git-commit: e3a1c1fde3809cb73b1bda091b8be43778515d1a
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 72%

---

# Résolution de l’écran

La [dimension](overview.md) « Résolution du moniteur » indique la hauteur et la largeur de l’affichage actif en pixels. Cette dimension est utile pour savoir où se trouve le « pli » de votre site pour les visiteurs ou pour connaître la largeur de la fenêtre de leur navigateur. Identifier l’emplacement du pli peut vous permettre d’optimiser l’affichage du contenu.

Cette dimension est différente de la [hauteur](browser-height.md) et de la [largeur](browser-width.md) du navigateur. La hauteur/largeur du navigateur correspond au nombre de pixels dans l’espace du navigateur consultable, tandis que la résolution de l’écran correspond au nombre de pixels de l’ensemble de l’écran. Si vous souhaitez voir la différence entre ces deux variables sur votre propre ordinateur, ouvrez la console du navigateur (F12 sur la plupart des navigateurs) et effectuez un copier-coller du code suivant dans la console :

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "; Browser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Les dimensions du navigateur sont toujours plus petites que la résolution de l’écran, car les dimensions du navigateur n’incluent ni la navigation ni les bordures du navigateur.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la chaîne de requête [`s`](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable JavaScript `screen.width` et `screen.height` dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi.

Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (par exemple via l’API), veillez à inclure le paramètre de chaîne de requête `s` dans les demandes d’image. Si la chaîne de requête `s` est manquante ou si une bibliothèque de collecte de données ne peut pas collecter la résolution du moniteur, ces données sont répertoriées sous [!UICONTROL `Not Specified`].

## Éléments de dimension

Les éléments de dimension incluent toutes les résolutions d’écran collectées. Les exemples de valeurs comprennent `1920 x 1080`, `1366 x 768` et `1280 x 720`.
