---
title: Semaine
description: La semaine au cours de laquelle la mesure a été effectuée.
feature: Dimensions
exl-id: 944ec843-998c-473f-b8e6-16cf126745b4
TQID: https://experienceleague.adobe.com/Vvr0Svg2khSzWbtWR5hLfveyctOEM-62WU6oxIsvzXs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 66%
---
# Semaine

La dimension [Semaine](overview.md) indique la semaine au cours de laquelle une mesure donnée a été effectuée. Le premier élément de dimension correspond à la première semaine de la période et le dernier élément de dimension correspond à la dernière semaine de la période. Cette dimension est essentielle pour les rapports de tendance, car elle vous permet d’afficher les mesures au fil du temps.

## Renseignement de cette dimension avec des données

Cette dimension est dérivée de la date et de l’heure de chaque accès. Aucune variable à définir ; elle est prête à l’emploi dans n’importe quelle mise en œuvre.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucune (dérivée de la date et heure de l’accès) |
| **Champ Web SDK/XDM** | Aucune (dérivée de la date et heure de l’accès) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | Hit |

## Éléments de dimension

Dans Analysis Workspace, les éléments de dimension comprennent la date (mois, jour et année) du premier jour de la semaine.

Dans Data Warehouse, les éléments de dimension comprennent des semaines numérotées en fonction de la période de la demande. Par exemple, la première semaine complète est `"Week 1"`. Si une requête inclut une semaine partielle, les données sont regroupées dans l’élément de dimension `"Week 0"`.
