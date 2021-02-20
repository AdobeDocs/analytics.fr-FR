---
title: État identifié
description: Indicateur déterminant la reconnaissance par le graphique d’appareil.
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 100%

---


# État identifié

La dimension « État identifié » est spécifique aux suites de rapports virtuelles d’[Analytics sur l’ensemble des appareils](../cda/overview.md). Elle indique si l’identifiant Experience Cloud ID est reconnu par le graphique d’appareil au moment de l’exécution du rapport. Cette dimension permet de comprendre comment Analytics sur l’ensemble des appareils assemble ou « compresse » les données.

## Renseignement de cette dimension avec des données

Tant qu’[Analytics sur l’ensemble des appareils](../cda/overview.md) est configuré pour une suite de rapports virtuelle, cette dimension est prête à l’emploi.

## Éléments de dimension

Les éléments de dimension comprennent `"Identified"` et `"Unidentified"`.

* **`"Identified"`** : le graphique d’appareil reconnaît l’identifiant Experience Cloud ID lié à l’accès.
* **`"Unidentified"`** : le graphique d’appareil ne reconnaît pas l’identifiant Experience Cloud ID ou l’accès ne comporte pas d’identifiant Experience Cloud ID.
