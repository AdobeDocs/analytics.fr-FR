---
title: Dimensions d’entrée
description: Liste les dimensions d’entrée et leur utilisation.
keywords: entry page, entry site section, entry server, entry custom insight
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---


# Dimensions d’entrée

*Cette page d’aide décrit le fonctionnement des entrées en tant que dimension. Pour plus d’informations sur le fonctionnement des entrées en tant que mesure, voir la mesure[Entrées](../metrics/entries.md).*

Les dimensions d’entrée sont basées sur les visites. Ils enregistrent le premier élément de dimension et le persistent pendant toute la durée de cette visite. Les dimensions d’entrée sont disponibles pour toutes les variables dont le cheminement est activé sous Variables [de](/help/admin/admin/c-traffic-variables/traffic-var.md) trafic dans les paramètres de la suite de rapports.

## Remplissage des dimensions d’entrée avec des données

Une dimension d’entrée donnée est basée sur sa variable de trafic associée. Si la variable de non-entrée comporte des données, sa dimension d’entrée associée contient également des données. Aucune modification d’implémentation n’est requise pour les dimensions d’entrée si vos variables de trafic contiennent des données.

## Éléments de dimension

Les variables d’entrée étant généralement basées sur des chaînes personnalisées dans votre implémentation, votre organisation détermine les éléments de dimension. Les valeurs d’une dimension d’entrée donnée correspondent aux éléments de dimension dans sa dimension de non-entrée associée. Par exemple, les éléments de dimension de la dimension &quot;Page d’entrée&quot; contiennent des éléments de dimension similaires dans la dimension &quot;Page&quot;.

## Origine de la page d’entrée

La dimension &quot;Page d’entrée d’origine&quot; fonctionne différemment des autres dimensions d’entrée. Au lieu de conserver la page d’entrée pour une visite donnée, elle conserve la toute première page d’entrée pour toute la vie du cookie de l’visiteur. Par exemple, si vous accédez au site pour `https://example.com/page4` votre première visite, puis qu’un an plus tard, accédez au site `https://example.com/store`, la dimension &quot;Page d’entrée d’origine&quot; est liste `https://example.com/page4` en tant qu’élément de dimension.
