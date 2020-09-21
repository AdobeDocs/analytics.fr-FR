---
title: Hauteur du navigateur - Regroupement
description: Hauteur de la fenêtre du navigateur en pixels.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '273'
ht-degree: 100%

---


# Hauteur du navigateur

La dimension « Hauteur du navigateur - regroupée » affiche la hauteur de la fenêtre du navigateur, classée en groupes de 100 pixels. Cette dimension est utile pour comprendre où se trouve le « pli » de votre site pour les visiteurs. Identifier l’emplacement du pli peut vous permettre d’optimiser l’affichage du contenu.

Cette dimension est différente de la hauteur d’écran. La hauteur du navigateur correspond au nombre de pixels dans l’espace consultable du navigateur, tandis que la hauteur d’écran correspond à la hauteur de l’ensemble du moniteur en pixels. Si vous souhaitez voir la différence entre ces deux variables sur votre propre ordinateur, ouvrez la console du navigateur (F12 sur la plupart des navigateurs) et effectuez un copier-coller du code suivant dans la console :

```javascript
"Browser height: " + window.innerHeight + " pixels\nScreen height: " + screen.height + " pixels";
```

La hauteur du navigateur est toujours inférieure ou égale à la hauteur d’écran, puisque la hauteur du navigateur n’inclut pas la navigation ou les bordures du navigateur.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la [`bh`chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable JavaScript `window.innerHeight` dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par le biais d’Adobe Experience Platform Launch, par exemple), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (via l’API, par exemple), veillez à inclure le paramètre de chaîne de requête `bh` lors du premier accès de chaque visite.

Adobe conserve la hauteur du navigateur pour une visite. Si la hauteur du navigateur est ajustée en cours de visite, l’ajustement n’est pas enregistré.

## Éléments de dimension

Les éléments de dimension comprennent toutes les hauteurs de navigateur collectées, classées en groupes de 100 pixels. Par exemple, si la hauteur du navigateur d’un accès correspond à `720`, elle est classée dans l’élément de dimension `700 to 799`.
