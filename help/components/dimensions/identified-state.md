---
title: État identifié
description: Indicateur déterminant la reconnaissance par le graphique d’appareil.
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 100%

---

# État identifié

La dimension « État identifié » est spécifique aux suites de rapports virtuelles d’[Analytics sur l’ensemble des appareils](../cda/overview.md). Il indique si les accès sont identifiés (regroupés) ou non par le système au moment de l’exécution du rapport. Cette dimension permet de comprendre comment Analytics sur l’ensemble des appareils assemble ou « compresse » les données.

## Renseignement de cette dimension avec des données

Tant qu’[Analytics sur l’ensemble des appareils](../cda/overview.md) est configuré pour une suite de rapports virtuelle, cette dimension est prête à l’emploi.

## Éléments de dimension

Les éléments de dimension comprennent `"Identified"` et `"Unidentified"`.

* **`"Identified"`**: l’accès est mappé à une personne.
* **`"Unidentified"`**: l’accès n’est pas mappé à une personne et n’a pu être mappé par aucune méthode d’attribution.
