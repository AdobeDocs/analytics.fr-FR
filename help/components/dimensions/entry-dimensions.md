---
title: Dimensions d’entrée
description: Liste les dimensions d’entrée et leur utilisation.
keywords: page d’accès, section d’entrée sur le site, serveur d’entrée, Custom Insight d’entrée
feature: Dimensions
exl-id: 424e2a9a-05ac-4397-921b-c8d7567348ed
source-git-commit: 43e483f157f1c2527f671eb43a165db86c77a7ce
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 98%

---

# Dimensions d’entrée

*Cette page d’aide décrit le fonctionnement des entrées en tant que dimension. Pour plus d’informations sur le fonctionnement des entrées en tant que mesure, consultez la mesure [Entrées](../metrics/entries.md).*

Les dimensions d’entrée sont [basée sur les visites](../metrics/visits.md). Elles enregistrent le premier élément de dimension et le conservent pendant toute la durée de cette visite. Les dimensions d’entrée sont disponibles pour toutes les variables dont le cheminement est activé sous [Variables de trafic](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) dans les paramètres de la suite de rapports.

## Renseignement des dimensions d’entrée avec des données

Une dimension d’entrée donnée est basée sur la variable de trafic qui lui est associée. Si la variable de non-entrée comporte des données, la dimension d’entrée associée contient également des données. Aucune modification de mise en œuvre n’est requise pour les dimensions d’entrée si vos variables de trafic contiennent des données.

## Éléments de dimension

Ces variables d’entrée étant généralement basées sur des chaînes personnalisées dans votre mise en œuvre, votre entreprise détermine les éléments de dimension. Les valeurs d’une dimension d’entrée donnée correspondent aux éléments de dimension dans la dimension de non-entrée qui lui est associée. Par exemple, les éléments de dimension de la dimension « Page d’accès » contiennent des éléments de dimension similaires à la dimension « Page ».

## Page d’accès d’origine

La dimension « Page d’accès d’origine » fonctionne différemment des autres dimensions d’entrée. Au lieu de conserver la page d’accès d’une visite donnée, elle conserve la toute première page d’accès pour toute la durée de vie du cookie de ce visiteur. Par exemple, si vous accédez au site pour la première fois via la page `https://example.com/page4` et que vous revenez sur le site un an plus tard via la page `https://example.com/store`, la dimension « Page d’accès d’origine » liste `https://example.com/page4` comme élément de dimension.
