---
title: Domaine
description: L’organisation ou le FAI que le visiteur utilise pour accéder à Internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
TQID: https://experienceleague.adobe.com/D-qRVSeU1Gx9YMDXvcDYLbSo9tCcR-0mUiD-2KsN3g4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 141
ht-degree: 54%

---

# Domaine

La [dimension](overview.md) « Domaine » indique les points d’accès utilisés par les visiteurs pour accéder à Internet.

## Renseignement de cette dimension avec des données

Adobe s’associe à [Digital Element](https://www.digitalelement.com/) pour déterminer le domaine du point d’accès. Plusieurs méthodes sont utilisées pour déterminer le domaine du point d’accès, dont la recherche DNS inversée. Il ne nécessite aucune configuration et ne dispose pas d’une variable à remplir.

* Pour les implémentations d’AppMeasurement, cette dimension est prête à l’emploi.
* Pour les implémentations de Web SDK, activez [!UICONTROL Recherche réseau] lors de la [configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

## Éléments de dimension

Les exemples d’éléments de dimension incluent `comcast.net`, `rr.com`, `sbcglobal.net` et `amazonaws.com`. Ces domaines sont des points d’accès et pas nécessairement le domaine représentant un FAI ou une organisation.

Les valeurs de dimension `None` signifient que le propriétaire de l’adresse IP du point d’accès n’a pas fourni de domaine.
