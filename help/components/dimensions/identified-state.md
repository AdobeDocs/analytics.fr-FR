---
title: État identifié
description: Indicateur déterminant la reconnaissance du groupement.
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: f75a1f6d9f08f422595c24760796abf0f8332ddb
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 83%

---

# État identifié

La [dimension](overview.md) « État identifié » est spécifique aux suites de rapports virtuelles [Analyses entre appareils](../cda/overview.md). Il indique si les accès sont identifiés (regroupés) ou non par le système au moment de l’exécution du rapport. Cette dimension permet de comprendre comment Analytics sur l’ensemble des appareils assemble ou « compresse » les données.

## Renseignement de cette dimension avec des données

Tant qu’[Analytics sur l’ensemble des appareils](../cda/overview.md) est configuré pour une suite de rapports virtuelle, cette dimension est prête à l’emploi.

## Éléments de dimension

Les éléments de dimension comprennent `"Identified"` et `"Unidentified"`.

* **`"Identified"`**: l’accès est mappé à une personne.
* **`"Unidentified"`**: l’accès n’est pas mappé à une personne et n’a pu être mappé par aucune méthode d’attribution.
