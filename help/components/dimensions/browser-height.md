---
title: Hauteur du navigateur - groupé
description: Hauteur de la fenêtre du navigateur en pixels.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# Hauteur du navigateur

La dimension &quot;Hauteur du navigateur - regroupée&quot; indique la hauteur de la fenêtre du navigateur, classée en groupes de 100 pixels. Cette dimension est utile pour comprendre où se trouve le &quot;pliage&quot; sur votre site pour les visiteurs. Comprendre où se trouve votre dossier peut vous permettre d’optimiser le contenu pour l’affichage.

Cette dimension est différente de la hauteur d’écran. La hauteur du navigateur correspond au nombre de pixels dans l’espace de navigation visible, tandis que la hauteur d’écran correspond à la hauteur de l’ensemble du moniteur, en pixels. Si vous souhaitez voir la différence entre ces deux variables sur votre propre ordinateur, ouvrez la console du navigateur (F12 sur la plupart des navigateurs) et copiez et collez le code suivant dans la console :

```javascript
"Browser height: " + window.innerHeight + " pixels\nScreen height: " + screen.height + " pixels";
```

La hauteur du navigateur est toujours inférieure ou égale à la hauteur d’écran, puisque la hauteur du navigateur n’inclut pas la navigation ni les bordures du navigateur.

## Renseigner cette dimension avec des données

Cette dimension récupère les données de la chaîne [`bh` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable JavaScript `window.innerHeight` dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par exemple par le biais du lancement d’Adobe Experience Platform), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (par exemple via l’API), veillez à inclure le paramètre de chaîne de `bh` requête au premier accès de chaque visite.

Adobe conserve la hauteur du navigateur pour une visite. Si la hauteur du navigateur est ajustée à la mi-visite, l’ajustement n’est pas enregistré.

## Éléments de dimension

Les éléments de dimension comprennent toutes les hauteurs de navigateur collectées, classées en groupes de 100 pixels. Par exemple, si la hauteur du navigateur d’un accès est `720`définie, elle est regroupée dans l’élément de dimension `700 to 799`.
