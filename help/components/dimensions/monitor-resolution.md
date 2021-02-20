---
title: Résolution de l’écran
description: Résolution en pixels de l’écran du visiteur.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 100%

---


# Résolution de l’écran

La dimension « Résolution de l’écran » indique la hauteur et la largeur de l’affichage actif en pixels. Cette dimension est utile pour savoir où se trouve le « pli » de votre site pour les visiteurs ou pour connaître la largeur de la fenêtre de leur navigateur. Identifier l’emplacement du pli peut vous permettre d’optimiser l’affichage du contenu.

Cette dimension est différente de la hauteur et de la largeur du navigateur. La hauteur/largeur du navigateur correspond au nombre de pixels dans l’espace du navigateur consultable, tandis que la résolution de l’écran correspond au nombre de pixels de l’ensemble de l’écran. Si vous souhaitez voir la différence entre ces deux variables sur votre propre ordinateur, ouvrez la console du navigateur (F12 sur la plupart des navigateurs) et effectuez un copier-coller du code suivant dans la console :

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Les dimensions du navigateur sont toujours plus petites que la résolution de l’écran, car les dimensions du navigateur n’incluent ni la navigation ni les bordures du navigateur.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la [`s`chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable JavaScript `screen.width` et `screen.height` dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par le biais d’Adobe Experience Platform Launch, par exemple), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (via l’API, par exemple), veillez à inclure le paramètre de chaîne de requête `s` dans les demandes d’image.

## Éléments de dimension

Les éléments de dimension incluent toutes les résolutions d’écran collectées. Les exemples de valeurs comprennent `1920 x 1080`, `1366 x 768` et `1280 x 720`.
