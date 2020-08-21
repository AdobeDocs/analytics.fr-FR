---
title: Dimensions d’entrée
description: Liste les dimensions d’entrée et leur utilisation.
keywords: entry page, entry site section, entry server, entry custom insight
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 58%

---


# Dimensions d’entrée

*Cette page d’aide décrit le fonctionnement des entrées en tant que dimension. Pour plus d’informations sur le fonctionnement des entrées en tant que mesure, consultez la mesure[Entrées](../metrics/entries.md).*

Les dimensions d’entrée sont basées sur les visites. Ils enregistrent le premier élément de dimension et le persistent pendant toute la durée de cette visite. Les dimensions d’entrée sont disponibles pour toutes les variables dont le cheminement est activé sous [Variables de trafic](/help/admin/admin/c-traffic-variables/traffic-var.md) dans les paramètres de la suite de rapports.

## Renseignement des dimensions d’entrée avec des données

Une dimension d’entrée donnée est basée sur la variable de trafic qui lui est associée. Si la variable de non-entrée comporte des données, la dimension d’entrée associée contient également des données. Aucune modification de mise en œuvre n’est requise pour les dimensions d’entrée si vos variables de trafic contiennent des données.

## Éléments de Dimension

Les variables d’entrée étant généralement basées sur des chaînes personnalisées dans votre implémentation, votre organisation détermine les éléments de dimension. Les valeurs d’une dimension d’entrée donnée correspondent aux éléments de dimension dans sa dimension de non-entrée associée. Par exemple, les éléments de dimension de la dimension &quot;Page d’entrée&quot; contiennent des éléments de dimension similaires dans la dimension &quot;Page&quot;.

## Page d’accès d’origine

La dimension « Page d’accès d’origine » fonctionne différemment des autres dimensions d’entrée. Au lieu de conserver la page d’accès d’une visite donnée, elle conserve la toute première page d’accès pour toute la durée de vie du cookie de ce visiteur. For example, if you land on `https://example.com/page4` for your first visit to the site, then a year later land on `https://example.com/store`, The &#39;Entry page original&#39; dimension lists `https://example.com/page4` as the dimension item.
