---
title: Profondeur de visite
description: Dimension basée sur la visite qui indique la profondeur de la visite.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---


# Profondeur de visite

La dimension &quot;Profondeur de visite&quot; indique le nombre de vues de page que le visiteur a vues au cours de toute la visite. La profondeur de visite augmente uniquement si l’accès est une vue de page et que la dimension [Page](page.md) n’est pas la même que l’élément de dimension Dernière vue de page. Il s’agit d’une dimension basée sur les visites, ce qui signifie qu’elle contient la même valeur pour la visite entière. Cette variable est définie pour tous les accès d’une visite une fois cette visite terminée.

## Renseigner cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Si une suite de rapports contient des données, cette dimension fonctionne.

## Éléments de dimension

Les éléments de dimension comprennent la chaîne `"Pages per visit"` suivie d’un nombre représentant le nombre de pages de la visite. L’élément de dimension de `"Pages per visit: 1"` représente une visite d’une seule page, tandis que l’élément de dimension `"Pages per visit: 8"` représente une visite de 8 vues de page (et tout nombre d’appels de suivi de liens).

## Comparaison avec la profondeur d’accès

Voir Profondeur [d’](hit-depth.md) accès pour une comparaison entre les dimensions.