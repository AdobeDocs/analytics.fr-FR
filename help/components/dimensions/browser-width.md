---
title: Largeur du navigateur - Regroupement
description: La largeur de la fenêtre du navigateur en pixels.
feature: Dimensions
exl-id: f0cb28b6-260b-4c3d-bbf8-17fae7ef22a0
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '274'
ht-degree: 100%

---

# Largeur du navigateur

La dimension « Largeur du navigateur - regroupée » affiche la largeur de la fenêtre du navigateur, classée en groupes de 100 pixels. Cette dimension s’avère utile lorsque vous souhaitez déterminer la largeur d’affichage dont bénéficie votre contenu auprès des visiteurs. Connaître la largeur d’affichage habituelle du contenu peut vous permettre d’optimiser le contenu pour l’affichage.

Cette dimension est différente de la largeur d’écran. La largeur du navigateur correspond au nombre de pixels dans l’espace du navigateur consultable, tandis que la largeur d’écran correspond à la largeur de l’ensemble du moniteur en pixels. Si vous souhaitez voir la différence entre ces deux variables sur votre propre ordinateur, ouvrez la console du navigateur (F12 sur la plupart des navigateurs) et effectuez un copier-coller du code suivant dans la console :

```javascript
"Browser width: " + window.innerWidth + " pixels\nScreen width: " + screen.width + " pixels";
```

La largeur du navigateur est toujours inférieure ou égale à la largeur d’écran, car elle ne comprend pas de barres de défilement ni de bordures.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la [`bw`chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable JavaScript `window.innerWidth` dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (via l’API, par exemple), veillez à inclure le paramètre de chaîne de requête `bw` lors du premier accès de chaque visite.

Adobe conserve la largeur du navigateur pour une visite. Si la largeur du navigateur est ajustée en cours de visite, l’ajustement n’est pas enregistré.

## Éléments de dimension

Les éléments de dimension comprennent toutes les largeurs de navigateur collectées, classées en groupes de 100 pixels. Par exemple, si la largeur du navigateur d’un accès correspond à `1280`, elle est classée dans l’élément de dimension `1200 to 1299`.
