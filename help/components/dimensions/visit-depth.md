---
title: Profondeur de visite
description: Dimension basée sur la visite et qui indique la profondeur de la visite.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 57%

---


# Profondeur de visite

La dimension « Profondeur de visite » indique le nombre de pages vues par le visiteur au cours de toute la visite. Visit depth increases only if the hit is a page view, and the [Page](page.md) dimension is not the same as the last page view&#39;s dimension item. Il s’agit d’une dimension basée sur les visites, ce qui signifie qu’elle contient la même valeur pour toute la visite. Cette variable est définie pour tous les accès d’une visite une fois la visite terminée.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de Dimension

Dimension items include the string `"Pages per visit"` followed by a number representing the number of pages in the visit. The dimension item of `"Pages per visit: 1"` represents a single-page visit, while the dimension item `"Pages per visit: 8"` represents a visit with 8 page views (and any number of link tracking calls).

## Comparaison avec la profondeur d’accès

Consultez la [Profondeur d’accès](hit-depth.md) pour une comparaison entre les dimensions.