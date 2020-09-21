---
title: Nombre de visites
description: La énième visite du visiteur.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '162'
ht-degree: 100%

---


# Nombre de visites

La dimension « Nombre de visites » indique le numéro de la visite actuelle du visiteur. Au début d’une nouvelle visite, cet élément de dimension augmente de 1. Cette dimension est utile lorsque vous souhaitez comprendre l’engagement des visiteurs lorsqu’ils reviennent sur votre site. Il s’agit d’une dimension basée sur les visites, ce qui signifie qu’elle contient la même valeur pour toute la visite et qu’elle ne peut pas être modifiée. Elle s’applique à la durée de vie du visiteur, quelle que soit la plage de dates du projet.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de dimension

Les éléments de dimension comprennent la chaîne `"Visit number"` suivie de la représentation numérique de la visite actuelle du visiteur. Par exemple, si le visiteur n’a jamais consulté votre site auparavant, sa première visite appartient à l’élément de dimension `"Visit number 1"`. S’il s’agit de la 13e visite du visiteur sur votre site, cette visite relève de l’élément de dimension `"Visit number 13"`.
