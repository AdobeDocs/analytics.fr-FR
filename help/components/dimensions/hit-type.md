---
title: Type d’accès
description: Détermine si l’accès est un accès en premier plan ou en arrière-plan.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 2%

---


# Type d’accès

La dimension &quot;Type d’accès&quot; détermine si une application mobile se trouvait au premier plan ou en arrière-plan lors de l’envoi de l’accès aux serveurs de collecte de données Adobe. Cette dimension s’applique uniquement aux suites de rapports qui contiennent des données pour les applications mobiles. Les données de navigateur collectées par AppMeasurement signalent toujours l’accès comme &quot;Premier plan&quot;.

## Renseigner cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations de SDK mobiles sur la version 4.13.6 ou ultérieure. Si vous n’utilisez pas le SDK mobile, tous les accès se liste sous la valeur de dimension &quot;Premier plan&quot;. If &quot;Disable Legacy Reporting and Attribution for Background Hits&quot; is checked, then background hits will show up only in [Virtual report suites](../vrs/vrs-mobile-visit-processing.md).

## Valeurs de dimension

Les valeurs de dimension incluent `"Foreground"` et `"Background"`. Tout accès qui n’a pas été envoyé en arrière-plan d’une application mobile appartient à la valeur de `"Foreground"` dimension. Tout accès envoyé lorsque l’application mobile se trouvait en arrière-plan appartient à la valeur de `"Background"` dimension.
