---
title: Jour de la semaine
description: Jour de la semaine, indépendamment de la plage de dates.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 4%

---


# Jour de la semaine

La dimension Jour de la semaine indique le jour de la semaine où l’accès a eu lieu. Ce rapport est utile si vous souhaitez qu’un rapport soit ventilé par semaine, mais que vous ne souhaitez pas qu’un jour statique soit considéré comme des éléments de dimension. Il s’avère particulièrement utile en tant que dimension dans les rapports planifiés, dans la mesure où cette dimension fonctionne avec n’importe quelle plage de dates.

## Renseigner cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Si une suite de rapports contient des données, cette dimension fonctionne.

## Éléments de dimension

Les éléments de dimension incluent `Sunday` - `Saturday`, représentant le jour de la semaine où l’accès a eu lieu. L’ordre des éléments de dimension respecte le premier jour de la semaine dans [Personnaliser le calendrier](/help/admin/admin/custom-calendar.md) par défaut.
