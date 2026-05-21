---
title: État identifié
description: Indicateur déterminant la reconnaissance du groupement.
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
TQID: https://experienceleague.adobe.com/JUBtgXBDboIgX0xbvuflF5q-oEwqHx4vKvJd0Y5XMLY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 111
ht-degree: 82%

---

# État identifié

La [dimension](overview.md) « État identifié » est spécifique aux suites de rapports virtuelles [Analyses entre appareils](../cda/overview.md). Il indique si les accès sont identifiés (regroupés) ou non par le système au moment de l’exécution du rapport. Cette dimension permet de comprendre comment Analytics sur l’ensemble des appareils assemble ou « compresse » les données.

## Renseignement de cette dimension avec des données

Tant qu’[Analytics sur l’ensemble des appareils](../cda/overview.md) est configuré pour une suite de rapports virtuelle, cette dimension est prête à l’emploi.

## Éléments de dimension

Les éléments de dimension comprennent `"Identified"` et `"Unidentified"`.

* **`"Identified"`**: l’accès est mappé à une personne.
* **`"Unidentified"`**: l’accès n’est pas mappé à une personne et n’a pu être mappé par aucune méthode d’attribution.
