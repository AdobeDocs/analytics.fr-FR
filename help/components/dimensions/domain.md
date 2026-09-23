---
title: Domaine
description: L’organisation ou le FAI que le visiteur utilise pour accéder à Internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
TQID: https://experienceleague.adobe.com/D-qRVSeU1Gx9YMDXvcDYLbSo9tCcR-0mUiD-2KsN3g4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
    internal-label: Methods
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 31%
---
# Domaine

La [dimension](overview.md) « Domaine » indique les points d’accès utilisés par les visiteurs pour accéder à Internet.

>[!NOTE]
>
>Data Warehouse comprend une dimension « [!UICONTROL Domaines] » (plural) retirée qui signale des informations similaires. Adobe recommande d’utiliser cette dimension, « [!UICONTROL Domain] » (au singulier), par souci de cohérence.

## Renseignement de cette dimension avec des données

Adobe dérive cette dimension côté serveur à partir de l’adresse IP du visiteur, en utilisant plusieurs méthodes, y compris la recherche DNS inversée pour déterminer le domaine du point d’accès. Adobe s’associe à [Digital Element](https://www.digitalelement.com/) pour gérer cette recherche. Aucune variable à définir.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucune (dérivée de l’adresse IP du visiteur) |
| **Champ Web SDK/XDM** | Aucune (dérivée de l’adresse IP du visiteur) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | S.O. |

* Pour les implémentations d’AppMeasurement, cette dimension est prête à l’emploi.
* Pour les implémentations de Web SDK, activez [!UICONTROL Recherche réseau] lors de la [configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

## Éléments de dimension

Les exemples d’éléments de dimension incluent `comcast.net`, `rr.com`, `sbcglobal.net` et `amazonaws.com`. Ces domaines sont des points d’accès et pas nécessairement le domaine représentant un FAI ou une organisation.

Les valeurs de dimension `None` signifient que le propriétaire de l’adresse IP du point d’accès n’a pas fourni de domaine.
