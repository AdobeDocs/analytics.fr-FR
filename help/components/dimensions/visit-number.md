---
title: Nombre de visites
description: La énième visite du visiteur.
translation-type: tm+mt
source-git-commit: 05ea2778cd5cd324c660fd0f1d2ac02373829f0f
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 0%

---


# Nombre de visites

Les rapports de dimension &quot;Nombre de visites&quot; qui se rendent sur le visiteur sont actuellement activés. Lorsqu’une nouvelle visite début, cette valeur de dimension augmente de 1. Cette dimension s’avère utile lorsque vous souhaitez comprendre comment les visiteurs s’impliquent lorsqu’ils reviennent sur votre site. Il s’agit d’une dimension basée sur les visites, ce qui signifie qu’elle contient la même valeur pour la visite entière et qu’elle ne peut pas être modifiée. Elle s’applique à la durée de vie du visiteur, quelle que soit la plage de dates du projet.

## Renseigner cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Si une suite de rapports contient des données, cette dimension fonctionne.

## Valeurs de dimension

Les valeurs de dimension comprennent la chaîne `"Visit number"` suivie de la représentation numérique de la visite sur laquelle se trouve actuellement le visiteur. Par exemple, si le visiteur n’a jamais été sur votre site auparavant, sa première visite appartient à la valeur de dimension `"Visit number 1"`. S’il s’agit de la 13e visite du visiteur sur votre site, ils appartiennent à la valeur de dimension `"Visit number 13"`.
