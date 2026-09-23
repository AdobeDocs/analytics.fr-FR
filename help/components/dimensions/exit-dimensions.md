---
title: Dimensions de sortie
description: Liste les dimensions de sortie et leur utilisation.
keywords: page de sortie, section de sortie du site, serveur de sortie, insight personnalisé de sortie
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
TQID: https://experienceleague.adobe.com/YRjvhW8OzBlip9ok0-1D4rYSljkccpIAlDkqCQv7nyo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
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
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 74%
---
# Dimensions de sortie

>[!BEGINSHADEBOX]

*Cette page d’aide décrit le fonctionnement des sorties en tant que [dimension](overview.md). Pour plus d’informations sur le fonctionnement des sorties en tant que mesure, consultez la mesure [Sorties](../metrics/exits.md).*

>[!ENDSHADEBOX]

Les dimensions de sortie enregistrent le dernier élément de dimension et l’appliquent rétroactivement à tous les hits de la visite. Les dimensions de sortie sont disponibles pour toutes les variables dont le cheminement est activé sous [Variables de trafic](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md) dans les paramètres de la suite de rapports.

## Renseignement des dimensions de sortie avec des données

Une dimension de sortie donnée est basée sur la variable de trafic qui lui est associée. Adobe dérive chaque dimension de sortie de la dernière valeur affichée pour cette variable au cours de la visite. Il n’y a pas de variable dédiée à définir. Si la variable de non-sortie comporte des données, la dimension de sortie associée contient également des données. Aucune modification de mise en œuvre n’est requise pour les dimensions de sortie si vos variables de trafic contiennent des données.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (dérivé du dernier accès du visiteur) |
| **Champ Web SDK/XDM** | Aucun (dérivé du dernier accès du visiteur) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | Visite |

## Éléments de dimension

Ces variables de sortie étant généralement basées sur des chaînes personnalisées dans votre mise en œuvre, votre entreprise détermine les éléments de dimension. Les valeurs d’une dimension de sortie donnée correspondent aux éléments de dimension dans la dimension de non-sortie qui lui est associée. Par exemple, les éléments de dimension de la dimension « Page de sortie » contiennent des éléments de dimension similaires à la dimension « Page ».
