---
title: Type d’accès
description: Détermine si l’accès est un accès en premier plan ou en arrière-plan.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 2%

---


# Type d’accès

La dimension &quot;Type d’accès&quot; détermine si une application mobile se trouvait au premier plan ou en arrière-plan lors de l’envoi de l’accès aux serveurs de collecte de données Adobe. Cette dimension s’applique uniquement aux suites de rapports qui contiennent des données pour les applications mobiles. Les données de navigateur collectées par AppMeasurement signalent toujours l’accès comme &quot;Premier plan&quot;.

## Renseigner cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations de SDK mobiles sur la version 4.13.6 ou ultérieure. Si vous n’utilisez pas le SDK mobile, tous les accès se liste sous l’élément de dimension &quot;Premier plan&quot;. If &quot;Disable Legacy Reporting and Attribution for Background Hits&quot; is checked, then background hits will show up only in [Virtual report suites](../vrs/vrs-mobile-visit-processing.md).

## Éléments de dimension

Les éléments de dimension incluent `"Foreground"` et `"Background"`. Tout accès qui n’a pas été envoyé en arrière-plan d’une application mobile appartient à l’élément de `"Foreground"` dimension. Tout accès envoyé lorsque l’application mobile se trouvait en arrière-plan appartient à l’élément de `"Background"` dimension.
