---
title: Largeur du navigateur - Regroupement
description: La largeur de la fenêtre du navigateur en pixels.
feature: Dimensions
exl-id: f0cb28b6-260b-4c3d-bbf8-17fae7ef22a0
TQID: https://experienceleague.adobe.com/f9AknIwL-9ZMJ8tnGMxpUNmlkQiFmbjI3gtlP3KZtSQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 274
ht-degree: 81%

---

# Largeur du navigateur

La dimension « Largeur du navigateur - compartimenté »](overview.md) affiche la largeur de la fenêtre du navigateur, classée dans des groupes prédéfinis. [Cette dimension s’avère utile lorsque vous souhaitez déterminer la largeur d’affichage dont bénéficie votre contenu auprès des visiteurs. Comprendre la largeur sur laquelle votre contenu est généralement affiché peut vous permettre d’optimiser ce contenu.

Cette dimension est différente de la largeur d’écran. La largeur du navigateur correspond au nombre de pixels dans l’espace du navigateur consultable, tandis que la largeur d’écran correspond à la largeur de l’ensemble du moniteur en pixels. Si vous souhaitez voir la différence entre ces deux variables sur votre propre ordinateur, ouvrez la console du navigateur (F12 sur la plupart des navigateurs) et effectuez un copier-coller du code suivant dans la console :

```javascript
console.log(`Browser width: ${window.innerWidth} pixels\nScreen width: ${screen.width} pixels`);
```

La largeur du navigateur est toujours inférieure ou égale à la largeur d’écran, car elle ne comprend pas de barres de défilement ni de bordures.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la chaîne de requête [`bw`](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable JavaScript `window.innerWidth` dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (via l’API, par exemple), veillez à inclure le paramètre de chaîne de requête `bw` lors du premier accès de chaque visite.

Adobe conserve la largeur du navigateur pour une visite. Si la largeur du navigateur est ajustée en cours de visite, l’ajustement n’est pas enregistré.

## Éléments de dimension

Les éléments Dimension incluent toutes les largeurs de navigateur collectées, classées dans des groupes prédéfinis. Par exemple, si la largeur du navigateur d’un accès correspond à `1280`, elle est classée dans l’élément de dimension `1200 to 1299`.
