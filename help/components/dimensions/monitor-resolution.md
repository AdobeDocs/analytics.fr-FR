---
title: Résolution de l’écran
description: Résolution en pixels du moniteur du visiteur.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 1%

---


# Résolution de l’écran

La dimension &quot;Résolution de l’écran&quot; indique la hauteur et la largeur de l’affichage actif en pixels. Cette dimension est utile lorsque vous souhaitez savoir où se trouve le &quot;pliage&quot; sur votre site pour les visiteurs ou quelle est la largeur de la fenêtre de leur navigateur pour les visiteurs. Comprendre où se trouve votre dossier peut vous permettre d’optimiser le contenu pour l’affichage.

Cette dimension est différente de la hauteur et de la largeur du navigateur. La hauteur/largeur du navigateur correspond au nombre de pixels dans l’espace de navigation affichable, tandis que la résolution du moniteur correspond au nombre de pixels dans l’ensemble du moniteur. Si vous souhaitez voir la différence entre ces deux variables sur votre propre ordinateur, ouvrez la console du navigateur (F12 sur la plupart des navigateurs) et copiez et collez le code suivant dans la console :

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Les dimensions du navigateur sont toujours plus petites que la résolution de l’écran, car les dimensions du navigateur n’incluent ni la navigation ni les bordures du navigateur.

## Renseigner cette dimension avec des données

Cette dimension récupère les données de la chaîne [`s` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable JavaScript `screen.width` et `screen.height` dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par exemple par le biais du lancement d’Adobe Experience Platform), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (par exemple via l’API), veillez à inclure le paramètre de chaîne de `s` requête dans les demandes d’image.

## Éléments de dimension

Les éléments de dimension incluent toutes les résolutions d&#39;écran collectées. Example values include `1920 x 1080`, `1366 x 768`, and `1280 x 720`.
