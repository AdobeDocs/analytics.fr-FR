---
title: Largeur du navigateur - cumulé
description: Largeur de la fenêtre du navigateur en pixels.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# Largeur du navigateur

La dimension Largeur du navigateur - regroupée affiche la largeur de la fenêtre du navigateur, classée en groupes de 100 pixels. Cette dimension s’avère utile lorsque vous souhaitez comprendre la largeur de l’affichage de votre contenu par les visiteurs. La compréhension de la largeur d’affichage du contenu peut vous permettre d’optimiser le contenu pour l’affichage.

Cette dimension est différente de la largeur d’écran. La largeur du navigateur est le nombre de pixels dans l’espace du navigateur affichable, tandis que la largeur de l’écran est la largeur de l’ensemble du moniteur en pixels. Si vous souhaitez voir la différence entre ces deux variables sur votre propre ordinateur, ouvrez la console du navigateur (F12 sur la plupart des navigateurs) et copiez et collez le code suivant dans la console :

```javascript
"Browser width: " + window.innerWidth + " pixels\nScreen width: " + screen.width + " pixels";
```

La largeur du navigateur est toujours inférieure ou égale à la largeur d’écran, car elle n’inclut pas de barres de défilement ni de bordures.

## Renseigner cette dimension avec des données

Cette dimension récupère les données de la chaîne [`bw` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable JavaScript `window.innerWidth` dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par exemple par le biais du lancement d’Adobe Experience Platform), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (par exemple via l’API), veillez à inclure le paramètre de chaîne de `bw` requête au premier accès de chaque visite.

Adobe conserve la largeur du navigateur pour une visite. Si la largeur du navigateur est ajustée en milieu de visite, l’ajustement n’est pas enregistré.

## Éléments de dimension

Les éléments de dimension comprennent toutes les largeurs de navigateur collectées, classées en groupes de 100 pixels. Par exemple, si la largeur du navigateur d’un accès est `1280`définie, il est regroupé dans l’élément de dimension `1200 to 1299`.
