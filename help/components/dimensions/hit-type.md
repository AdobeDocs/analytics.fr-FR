---
title: Type d’accès
description: Détermine si l’accès est un accès de premier plan ou en arrière-plan.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 84%

---

# Type d’accès

&quot;Type d’accès&quot; [dimension](overview.md) détermine si une application mobile se trouvait au premier plan ou en arrière-plan lorsque l’accès a été envoyé aux serveurs de collecte de données d’Adobe. Cette dimension s’applique uniquement aux suites de rapports qui contiennent des données pour les applications mobiles. Les données de navigateur collectées par AppMeasurement indiquent toujours l’accès comme « Premier plan ».

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations de SDK mobile sur la version 4.13.6 ou ultérieure. Si vous n’utilisez pas le SDK mobile, tous les accès sont répertoriés sous l’élément de dimension « Premier plan ». Si la case « Désactiver la création de rapports et l’attribution héritées pour les accès en arrière-plan » est activée, les accès en arrière-plan n’apparaissent que dans les [suites de rapports virtuelles](../vrs/vrs-mobile-visit-processing.md).

## Éléments de dimension

Les éléments de dimension comprennent `"Foreground"` et `"Background"`. Tout accès qui n’a pas été envoyé en arrière-plan d’une application mobile appartient à l’élément de dimension `"Foreground"`. Tout accès envoyé lorsque l’application mobile se trouvait en arrière-plan appartient à l’élément de dimension `"Background"`.
