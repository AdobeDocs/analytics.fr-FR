---
title: Profondeur de visite
description: Dimension basée sur la visite et qui indique la profondeur de la visite.
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
TQID: https://experienceleague.adobe.com/mT5dQzR6edNpvU6Fbf9LlLwQuxW6RA-ZCZJDaIFkyAw
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
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
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
source-wordcount: '209'
ht-degree: 68%
---
# Profondeur de visite

La [dimension](overview.md) « Profondeur de la visite » indique le nombre de pages vues par le visiteur au cours de la visite complète. La profondeur de visite augmente uniquement si le hit est une page vue et si la dimension [Page](page.md) n’est pas la même que celle de l’élément de dimension de la dernière page vue. Il s’agit d’une dimension basée sur les visites, ce qui signifie qu’elle contient la même valeur pour toute la visite. Cette variable est définie pour tous les hits d’une visite une fois la visite terminée.

## Renseignement de cette dimension avec des données

Adobe calcule cette dimension côté serveur à partir des pages vues lors de chaque visite. Il n’existe aucune variable à définir ; elle est prête à l’emploi pour toutes les implémentations.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (calculé par Adobe) |
| **Champ Web SDK/XDM** | Aucun (calculé par Adobe) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | Visite |

## Éléments de dimension

Les éléments de dimension comprennent la chaîne `"Pages per visit"` suivie d’un nombre représentant le nombre de pages dans la visite. L’élément de dimension de `"Pages per visit: 1"` représente une visite de page unique, tandis que l’élément de dimension `"Pages per visit: 8"` représente une visite avec 8 pages vues (et tout nombre d’appels de suivi des liens).

## Comparaison avec la profondeur de hit

Consultez la [Profondeur de hit](hit-depth.md) pour une comparaison entre les dimensions.
