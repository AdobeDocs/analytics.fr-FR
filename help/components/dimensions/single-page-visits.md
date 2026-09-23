---
title: Visites sur une seule page (dimensions)
description: Indicateur précisant que la visite ne comportait qu’une seule page
feature: Dimensions
exl-id: f7b58941-add4-4e7b-8645-a64280fd9dcb
TQID: https://experienceleague.adobe.com/mMxxlVpQi7IsSuxSZGijnvWeoqCa-ybf8otPRDf6AyQ
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
source-wordcount: '187'
ht-degree: 64%
---
# Visites de page unique

>[!BEGINSHADEBOX]

*Cette page d’aide décrit le fonctionnement des « visites sur une seule page » en tant que [dimension](overview.md). Pour plus d’informations, consultez la mesure [Visites de page unique](../metrics/single-page-visits.md).*

>[!ENDSHADEBOX]

La dimension « Visites de page unique » indique le nombre de visites qui ne comportaient qu’un élément de dimension [Page](page.md). Il s’agit de la forme de dimension correspondante à la mesure [Visites de page unique](../metrics/single-page-visits.md).

Cette dimension est généralement utilisée comme composant dans la [segmentation](../segmentation/seg-home.md). Elle n’est généralement pas utilisée comme dimension dans les rapports.

## Renseignement de cette dimension avec des données

Adobe calcule cette dimension côté serveur en évaluant si chaque visite contenait une seule page unique. Il n’existe aucune variable à définir ; elle est prête à l’emploi pour toutes les implémentations.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (calculé par Adobe) |
| **Champ Web SDK/XDM** | Aucun (calculé par Adobe) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | S.O. |

## Éléments de dimension

Le seul élément de dimension est `"Enabled"`. Si une visite ne comporte qu’une page, le hit est défini sur cette valeur. Tous les autres hits sont omis de ce rapport.
