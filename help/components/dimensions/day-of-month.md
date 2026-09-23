---
title: Jour du mois
description: Jour numérique du mois, quel que soit le mois.
feature: Dimensions
exl-id: 6d27aa9f-ce75-4a27-bb92-3acabe3975a1
TQID: https://experienceleague.adobe.com/jSrKlf4a5f-6MTrQwwUcvRJep4chAUyOsj5hFjE1HRg
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
source-wordcount: '180'
ht-degree: 63%
---
# Jour du mois

La [dimension](overview.md) « Jour du mois » indique le jour numérique d’un mois donné en tant qu’élément de dimension. Si, par exemple, vous disposez d’un rapport couvrant la période du 1er janvier au 31 mars, le premier de chaque mois est placé dans le même élément de dimension. Ce rapport est utile si vous souhaitez un rapport divisé par jour, mais ne souhaitez pas une date statique comme élément de dimension. Il s’avère particulièrement utile comme dimension dans les rapports planifiés, dans la mesure où cette dimension s’adapte à la période sélectionnée.

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

Les éléments de dimension comprennent les nombres `1` à `31`, représentant le jour du mois où le hit a eu lieu.
