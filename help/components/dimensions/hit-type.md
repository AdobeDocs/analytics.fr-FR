---
title: Type d’accès
description: Détermine si l’accès est un accès de premier plan ou en arrière-plan.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
TQID: https://experienceleague.adobe.com/6G-XpOMMZGum9LAQzKn0zGdeNRmHFPpmYizqRrbKuUE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: c77ba355-6681-41fe-b719-563d3f507fdbid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 34%

---

# Type d’accès

La [dimension](overview.md) « Type d’accès » détermine si une application mobile se trouvait au premier plan ou en arrière-plan lorsque l’accès a été envoyé aux serveurs de collecte de données d’Adobe. Cette dimension s’applique uniquement aux suites de rapports qui contiennent des données pour les applications mobiles. Les données de navigateur collectées via AppMeasurement signalent toujours l’accès comme `"Foreground"`.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations de SDK mobile sur la version 4.13.6 ou ultérieure. Le SDK mobile définit la variable de [`customerPerspective`](/help/implement/vars/page-vars/customerperspective.md) (paramètre de requête `cp`) pour indiquer si chaque accès s’est produit au premier plan ou en arrière-plan. Si vous n’utilisez pas le SDK mobile, tous les accès sont répertoriés sous `"Foreground"`. Si l’option **[!UICONTROL Empêcher les accès en arrière-plan de démarrer une nouvelle visite]** est sélectionnée lors de la configuration d’une [suite de rapports virtuelle](../vrs/vrs-mobile-visit-processing.md), les accès en arrière-plan ne gonflent pas [[!UICONTROL Visites]](../metrics/visits.md) et [[!UICONTROL Visiteurs uniques]](../metrics/unique-visitors.md).

## Éléments de dimension

Les éléments de dimension comprennent `"Foreground"` et `"Background"`. Les accès en arrière-plan se produisent uniquement sur les appareils mobiles sur lesquels l’application suivie se trouve en arrière-plan.
