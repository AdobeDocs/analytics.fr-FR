---
title: Type d’accès
description: Détermine si l’accès est un accès de premier plan ou en arrière-plan.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
TQID: https://experienceleague.adobe.com/6G-XpOMMZGum9LAQzKn0zGdeNRmHFPpmYizqRrbKuUE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 84%

---

# Type d’accès

La [dimension](overview.md) « Type d’accès » détermine si une application mobile se trouvait au premier plan ou en arrière-plan lorsque l’accès a été envoyé aux serveurs de collecte de données d’Adobe. Cette dimension s’applique uniquement aux suites de rapports qui contiennent des données pour les applications mobiles. Les données de navigateur collectées par AppMeasurement indiquent toujours l’accès comme « Premier plan ».

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations de SDK mobile sur la version 4.13.6 ou ultérieure. Si vous n’utilisez pas le SDK mobile, tous les accès sont répertoriés sous l’élément de dimension « Premier plan ». Si la case « Désactiver la création de rapports et l’attribution héritées pour les accès en arrière-plan » est activée, les accès en arrière-plan n’apparaissent que dans les [suites de rapports virtuelles](../vrs/vrs-mobile-visit-processing.md).

## Éléments de dimension

Les éléments de dimension comprennent `"Foreground"` et `"Background"`. Tout accès qui n’a pas été envoyé en arrière-plan d’une application mobile appartient à l’élément de dimension `"Foreground"`. Tout accès envoyé lorsque l’application mobile se trouvait en arrière-plan appartient à l’élément de dimension `"Background"`.
