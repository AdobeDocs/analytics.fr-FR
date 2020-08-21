---
title: Nombre de visites
description: La énième visite du visiteur.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 59%

---


# Nombre de visites

La dimension « Nombre de visites » indique le numéro de la visite actuelle du visiteur. Lorsqu’une nouvelle visite début, cet élément de dimension augmente de 1. Cette dimension est utile lorsque vous souhaitez comprendre l’engagement des visiteurs lorsqu’ils reviennent sur votre site. Il s’agit d’une dimension basée sur les visites, ce qui signifie qu’elle contient la même valeur pour toute la visite et qu’elle ne peut pas être modifiée. Elle s’applique à la durée de vie du visiteur, quelle que soit la plage de dates du projet.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de Dimension

Dimension items include the string `"Visit number"` followed by the numeric representation of the visit the visitor is currently on. For example, if the visitor has never been to your site before, their first visit belongs to the dimension item `"Visit number 1"`. If this is the visitor&#39;s 13th visit to your site, they belong to the dimension item `"Visit number 13"`.
