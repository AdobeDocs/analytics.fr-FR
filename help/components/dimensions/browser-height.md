---
title: Hauteur du navigateur - Regroupement
description: Hauteur de la fenêtre du navigateur en pixels.
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
TQID: https://experienceleague.adobe.com/-MSFtBJDaiG0yYL6ZdpzbPY80uFJbdxB0gyBtKAkFzY
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
ht-degree: 40%
---
# Hauteur du navigateur

La dimension « Hauteur du navigateur - regroupé »](overview.md) affiche la hauteur de la fenêtre du navigateur, classée en groupes prédéfinis. [Cette dimension est utile pour comprendre où se trouve le « pli » de votre site pour les visiteurs. Identifier l’emplacement du pli peut vous permettre d’optimiser l’affichage du contenu.

Cette dimension est différente de la hauteur d’écran. La hauteur du navigateur correspond au nombre de pixels dans l’espace consultable du navigateur, tandis que la hauteur d’écran correspond à la hauteur de l’ensemble du moniteur en pixels. Si vous souhaitez voir la différence entre ces deux variables sur votre propre ordinateur, ouvrez la console du navigateur (F12 sur la plupart des navigateurs) et effectuez un copier-coller du code suivant dans la console :

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

La hauteur du navigateur est généralement inférieure ou égale à la hauteur d’écran, car la hauteur du navigateur n’inclut pas la navigation du navigateur ou les bordures.

>[!NOTE]
>
>Data Warehouse fournit également une dimension « [!UICONTROL Hauteur du navigateur - granulaire] », qui indique la hauteur exacte en pixels au lieu de regrouper les valeurs dans des intervalles prédéfinis.

## Renseignement de cette dimension avec des données

La hauteur du navigateur est collectée automatiquement, côté client, à partir de la propriété `window.innerHeight` du navigateur. Elle est prête à l’emploi dans toute implémentation d’AppMeasurement ou de Web SDK (balises). Il n’y a aucune variable à définir. Si vous collectez des données en dehors d’AppMeasurement ou de Web SDK (par exemple via l’API), envoyez la valeur lors du premier accès de chaque visite. Si la hauteur du navigateur est ajustée en milieu de visite, l’ajustement n’est pas enregistré.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (collecté automatiquement) |
| **Champ Web SDK/XDM** | Aucun (collecté automatiquement) |
| **Paramètre de requête** | [`bh`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<browserHeight>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Plage de valeurs** | 0-65 535 |
| **Persistance** | Visite |

## Éléments de dimension

Les éléments Dimension incluent toutes les hauteurs de navigateur collectées, classées dans des groupes prédéfinis. Par exemple, si la hauteur du navigateur d’un hit correspond à `720`, elle est classée dans l’élément de dimension `700 to 799`.
