---
title: Largeur du navigateur - Regroupement
description: La largeur de la fenêtre du navigateur en pixels.
feature: Dimensions
exl-id: f0cb28b6-260b-4c3d-bbf8-17fae7ef22a0
TQID: https://experienceleague.adobe.com/f9AknIwL-9ZMJ8tnGMxpUNmlkQiFmbjI3gtlP3KZtSQ
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
source-wordcount: '318'
ht-degree: 45%
---
# Largeur du navigateur

La dimension « Largeur du navigateur - compartimenté »[&#128279;](overview.md) affiche la largeur de la fenêtre du navigateur, classée dans des groupes prédéfinis. Cette dimension s’avère utile lorsque vous souhaitez déterminer la largeur d’affichage dont bénéficie votre contenu auprès des visiteurs. Comprendre la largeur sur laquelle votre contenu est généralement affiché peut vous permettre d’optimiser ce contenu.

Cette dimension est différente de la largeur d’écran. La largeur du navigateur correspond au nombre de pixels dans l’espace du navigateur consultable, tandis que la largeur d’écran correspond à la largeur de l’ensemble du moniteur en pixels. Si vous souhaitez voir la différence entre ces deux variables sur votre propre ordinateur, ouvrez la console du navigateur (F12 sur la plupart des navigateurs) et effectuez un copier-coller du code suivant dans la console :

```javascript
console.log(`Browser width: ${window.innerWidth} pixels\nScreen width: ${screen.width} pixels`);
```

La largeur du navigateur est toujours inférieure ou égale à la largeur d’écran, car elle ne comprend pas de barres de défilement ni de bordures.

>[!NOTE]
>
>Data Warehouse fournit également une dimension « [!UICONTROL Largeur du navigateur - granulaire] » qui indique la largeur exacte en pixels au lieu de regrouper les valeurs dans des intervalles prédéfinis.

## Renseignement de cette dimension avec des données

La largeur du navigateur est collectée automatiquement, côté client, à partir de la propriété `window.innerWidth` du navigateur. Elle est prête à l’emploi dans toute implémentation d’AppMeasurement ou de Web SDK (balises). Il n’y a aucune variable à définir. Si vous collectez des données en dehors d’AppMeasurement ou de Web SDK (par exemple via l’API), envoyez la valeur lors du premier accès de chaque visite. Si la largeur du navigateur est ajustée en cours de visite, l’ajustement n’est pas enregistré.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (collecté automatiquement) |
| **Champ Web SDK/XDM** | Aucun (collecté automatiquement) |
| **Paramètre de requête** | [`bw`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<browserWidth>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Plage de valeurs** | 0-65 535 |
| **Persistance** | Visite |

## Éléments de dimension

Les éléments Dimension incluent toutes les largeurs de navigateur collectées, classées dans des groupes prédéfinis. Par exemple, si la largeur du navigateur d’un hit correspond à `1280`, elle est classée dans l’élément de dimension `1200 to 1299`.
