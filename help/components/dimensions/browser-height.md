---
title: Hauteur du navigateur - Regroupement
description: Hauteur de la fenêtre du navigateur en pixels.
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
TQID: https://experienceleague.adobe.com/-MSFtBJDaiG0yYL6ZdpzbPY80uFJbdxB0gyBtKAkFzY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 273
ht-degree: 87%

---

# Hauteur du navigateur

La dimension « Hauteur du navigateur - regroupé »](overview.md) affiche la hauteur de la fenêtre du navigateur, classée en groupes prédéfinis. [Cette dimension est utile pour comprendre où se trouve le « pli » de votre site pour les visiteurs. Identifier l’emplacement du pli peut vous permettre d’optimiser l’affichage du contenu.

Cette dimension est différente de la hauteur d’écran. La hauteur du navigateur correspond au nombre de pixels dans l’espace consultable du navigateur, tandis que la hauteur d’écran correspond à la hauteur de l’ensemble du moniteur en pixels. Si vous souhaitez voir la différence entre ces deux variables sur votre propre ordinateur, ouvrez la console du navigateur (F12 sur la plupart des navigateurs) et effectuez un copier-coller du code suivant dans la console :

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

La hauteur du navigateur est toujours inférieure ou égale à la hauteur d’écran, puisque la hauteur du navigateur n’inclut pas la navigation ou les bordures du navigateur.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la chaîne de requête [`bh`](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable JavaScript `window.innerHeight` dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (via l’API, par exemple), veillez à inclure le paramètre de chaîne de requête `bh` lors du premier accès de chaque visite.

Adobe conserve la hauteur du navigateur pour une visite. Si la hauteur du navigateur est ajustée en cours de visite, l’ajustement n’est pas enregistré.

## Éléments de dimension

Les éléments Dimension incluent toutes les hauteurs de navigateur collectées, classées dans des groupes prédéfinis. Par exemple, si la hauteur du navigateur d’un accès correspond à `720`, elle est classée dans l’élément de dimension `700 to 799`.
