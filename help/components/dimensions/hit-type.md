---
title: Type d’accès
description: Détermine si l’accès est un accès de premier plan ou en arrière-plan.
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '163'
ht-degree: 100%

---

# Type d’accès

La dimension « Type d’accès » détermine si une application mobile se trouvait au premier plan ou en arrière-plan lorsque l’accès a été envoyé aux serveurs de collecte de données Adobe. Cette dimension s’applique uniquement aux suites de rapports qui contiennent des données pour les applications mobiles. Les données de navigateur collectées par AppMeasurement indiquent toujours l’accès comme « Premier plan ».

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations de SDK mobile sur la version 4.13.6 ou ultérieure. Si vous n’utilisez pas le SDK mobile, tous les accès sont répertoriés sous l’élément de dimension « Premier plan ». Si la case « Désactiver la création de rapports et l’attribution héritées pour les accès en arrière-plan » est activée, les accès en arrière-plan n’apparaissent que dans les [suites de rapports virtuelles](../vrs/vrs-mobile-visit-processing.md).

## Éléments de dimension

Les éléments de dimension comprennent `"Foreground"` et `"Background"`. Tout accès qui n’a pas été envoyé en arrière-plan d’une application mobile appartient à l’élément de dimension `"Foreground"`. Tout accès envoyé lorsque l’application mobile se trouvait en arrière-plan appartient à l’élément de dimension `"Background"`.
