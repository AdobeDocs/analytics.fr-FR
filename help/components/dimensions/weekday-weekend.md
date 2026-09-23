---
title: Jour ouvrable/week-end
description: Détermine si le hit s’est produit pendant un jour ouvrable ou le week-end.
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
TQID: https://experienceleague.adobe.com/9TJv-49ub1zHsgEGtBeoJVoHhsBktlOr7QhmgLdLRSo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
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
source-wordcount: '155'
ht-degree: 49%
---
# Jour ouvrable/week-end

La [dimension](overview.md) Jour de la semaine/week-end indique si l’accès a eu lieu un jour de la semaine (lundi à vendredi) ou un week-end (samedi à dimanche) dans insight. L’heure du hit est basée sur le [fuseau horaire de la suite de rapports](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Renseignement de cette dimension avec des données

Cette dimension est dérivée de la date et de l’heure de chaque accès ; il n’y a aucune variable à définir. Sa seule dépendance est le fuseau horaire de la suite de rapports, qui détermine le jour de la semaine pour chaque accès.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucune (dérivée de la date et heure de l’accès) |
| **Champ Web SDK/XDM** | Aucune (dérivée de la date et heure de l’accès) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | Hit |

## Éléments de dimension

Cette dimension contient toujours exactement deux éléments de dimension : `"Weekday"` et `"Weekend"`. L’élément de dimension `"Weekday"` s’applique à tous les hits du lundi au vendredi, tandis que l’élément de dimension `"Weekend"` s’applique à tous les hits du samedi au dimanche.
