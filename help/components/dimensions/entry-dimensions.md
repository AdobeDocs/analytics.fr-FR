---
title: Dimensions d’entrée
description: Liste les dimensions d’entrée et leur utilisation.
keywords: page d’accès, section d’entrée sur le site, serveur d’entrée, Custom Insight d’entrée
feature: Dimensions
exl-id: 424e2a9a-05ac-4397-921b-c8d7567348ed
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 75%

---

# Dimensions d’entrée

*Cette page d’aide décrit le fonctionnement des entrées en tant que [dimension](overview.md). Pour plus d’informations sur le fonctionnement des entrées en tant que mesure, consultez la mesure [Entrées](../metrics/entries.md).*

Les dimensions d’entrée sont [basées sur les visites](../metrics/visits.md). Elles enregistrent le premier élément de dimension et le conservent pendant toute la durée de cette visite. Les dimensions d’entrée sont disponibles pour toutes les variables dont le cheminement est activé sous [Variables de trafic](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) dans les paramètres de la suite de rapports.

>[!TIP]
>Si vous souhaitez afficher les données en fonction du premier accès d’une visite au lieu de la première valeur affichée dans une visite, vous pouvez utiliser un [segment](/help/components/segmentation/seg-overview.md). Utilisez un conteneur d’accès pour lequel [Profondeur d’accès](hit-depth.md) est égal à 1, puis utilisez ce segment avec la variable souhaitée.

## Renseignement des dimensions d’entrée avec des données

Une entrée donnée [dimension](overview.md) est basée sur la variable de trafic qui lui est associée. Si la variable de non-entrée comporte des données, la dimension d’entrée associée contient également des données. Aucune modification de mise en œuvre n’est requise pour les dimensions d’entrée si vos variables de trafic contiennent des données.

## Éléments de dimension

Ces variables d’entrée étant généralement basées sur des chaînes personnalisées dans votre mise en œuvre, votre entreprise détermine les éléments de dimension. Les valeurs d’une dimension d’entrée donnée correspondent aux éléments de dimension dans la dimension de non-entrée qui lui est associée. Par exemple, les éléments de dimension de la dimension « Page d’accès » contiennent des éléments de dimension similaires à la dimension « Page ».

## Page d’accès d’origine

La dimension « Page d’accès d’origine » fonctionne différemment des autres dimensions d’entrée. Au lieu de conserver la page d’accès d’une visite donnée, elle conserve la toute première page d’accès pour toute la durée de vie du cookie de ce visiteur. Par exemple, si vous accédez au site pour la première fois via la page `https://example.com/page4` et que vous revenez sur le site un an plus tard via la page `https://example.com/store`, la dimension « Page d’accès d’origine » liste `https://example.com/page4` comme élément de dimension.
