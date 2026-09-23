---
title: État identifié
description: Indicateur déterminant la reconnaissance du groupement.
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
TQID: https://experienceleague.adobe.com/JUBtgXBDboIgX0xbvuflF5q-oEwqHx4vKvJd0Y5XMLY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 46%
---
# État identifié

La [dimension](overview.md) « État identifié » est spécifique aux suites de rapports virtuelles [Analyses entre appareils](../cda/overview.md). Il indique si les hits sont identifiés (regroupés) ou non par le système au moment de l’exécution du rapport. Cette dimension permet de comprendre l’efficacité du rapprochement ou de la « compression » des données par CDA.

## Renseignement de cette dimension avec des données

Cette dimension est calculée par [Analyses entre appareils](../cda/overview.md) au moment de l’exécution d’un rapport, en fonction de si chaque accès a été associé à une personne. Tant qu’Analytics sur l’ensemble des appareils est configuré pour une suite de rapports virtuelle, elle fonctionne prête à l’emploi ; il n’y a aucune variable à définir.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (calculé par les analyses entre appareils) |
| **Champ Web SDK/XDM** | Aucun (calculé par les analyses entre appareils) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | S.O. |

## Éléments de dimension

Les éléments de dimension comprennent `"Identified"` et `"Unidentified"`.

* **`"Identified"`** : le hit est mappé à une personne.
* **`"Unidentified"`** : le hit n’est pas mappé à une personne et n’a pu être mappé par aucune méthode d’attribution.
