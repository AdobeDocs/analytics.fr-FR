---
title: État identifié
description: Indicateur déterminant la reconnaissance par le graphique du périphérique.
translation-type: tm+mt
source-git-commit: 60fe85adaebee8ca390e59727dda949c12c1ee26
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 9%

---


# État identifié

La dimension &quot;État identifié&quot; est spécifique aux suites de rapports virtuelles Analytics [](../cda/overview.md) sur plusieurs périphériques. Il indique si l&#39;ID d&#39;Experience Cloud est reconnu par le graphique du périphérique au moment de l&#39;exécution du rapport. Cette dimension permet de comprendre comment l&#39;ADC recoupe ou &quot;compresse&quot; les données.

## Renseignement de cette dimension avec des données

Tant que Analytics [](../cda/overview.md) sur plusieurs périphériques est configuré pour une suite de rapports virtuelle, cette dimension est prête à l’emploi.

## Éléments de dimension

Les éléments de dimension comprennent `"Identified"` et `"Unidentified"`.

* **`"Identified"`**: Le graphique du périphérique reconnaît l’ID d’Experience Cloud lié à l’accès.
* **`"Unidentified"`**: Le graphique du périphérique ne reconnaît pas l’ID d’Experience Cloud ou l’accès ne comporte pas d’ID d’Experience Cloud.
