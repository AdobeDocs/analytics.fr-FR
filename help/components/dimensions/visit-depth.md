---
title: Profondeur de visite
description: Dimension basée sur la visite et qui indique la profondeur de la visite.
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '166'
ht-degree: 100%

---

# Profondeur de visite

La dimension « Profondeur de visite » indique le nombre de pages vues par le visiteur au cours de toute la visite. La profondeur de visite augmente uniquement si l’accès est une page vue et si la dimension [Page](page.md) n’est pas la même que celle de l’élément de dimension de la dernière page vue. Il s’agit d’une dimension basée sur les visites, ce qui signifie qu’elle contient la même valeur pour toute la visite. Cette variable est définie pour tous les accès d’une visite une fois la visite terminée.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de dimension

Les éléments de dimension comprennent la chaîne `"Pages per visit"` suivie d’un nombre représentant le nombre de pages dans la visite. L’élément de dimension de `"Pages per visit: 1"` représente une visite de page unique, tandis que l’élément de dimension `"Pages per visit: 8"` représente une visite avec 8 pages vues (et tout nombre d’appels de suivi des liens).

## Comparaison avec la profondeur d’accès

Consultez la [Profondeur d’accès](hit-depth.md) pour une comparaison entre les dimensions.
