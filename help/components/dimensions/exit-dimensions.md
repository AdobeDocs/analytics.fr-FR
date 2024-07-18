---
title: Dimensions de sortie
description: Liste les dimensions de sortie et leur utilisation.
keywords: page de sortie, section du site de sortie, serveur de sortie, Custom Insight de sortie
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 94%

---

# Dimensions de sortie

*Cette page d’aide décrit le fonctionnement des sorties en tant que [dimension](overview.md). Pour plus d’informations sur le fonctionnement des sorties en tant que mesure, consultez la mesure [Sorties](../metrics/exits.md).*

Les dimensions de sortie enregistrent le dernier élément de dimension et l’appliquent rétroactivement à tous les accès de la visite. Les dimensions de sortie sont disponibles pour toutes les variables dont le cheminement est activé sous [Variables de trafic](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) dans les paramètres de la suite de rapports.

## Renseignement des dimensions de sortie avec des données

Une dimension de sortie donnée est basée sur la variable de trafic qui lui est associée. Si la variable de non-sortie comporte des données, la dimension de sortie associée contient également des données. Aucune modification de mise en œuvre n’est requise pour les dimensions de sortie si vos variables de trafic contiennent des données.

## Éléments de dimension

Ces variables de sortie étant généralement basées sur des chaînes personnalisées dans votre mise en œuvre, votre entreprise détermine les éléments de dimension. Les valeurs d’une dimension de sortie donnée correspondent aux éléments de dimension dans la dimension de non-sortie qui lui est associée. Par exemple, les éléments de dimension de la dimension « Page de sortie » contiennent des éléments de dimension similaires à la dimension « Page ».
