---
title: Jour du mois
description: Jour numérique du mois, quel que soit le mois.
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 4%

---


# Jour du mois

La dimension &quot;Jour du mois&quot; signale le jour numérique d’un mois donné comme valeur de dimension. Si, par exemple, vous disposez d’un rapport qui s’étend du 1er au 31 mars, le premier de chaque mois est regroupé dans la même valeur de dimension. Ce rapport est utile si vous souhaitez qu’un rapport soit ventilé par jour, mais que vous ne souhaitez pas qu’une date statique soit une valeur de dimension. Il s’avère particulièrement utile en tant que dimension dans les rapports planifiés, dans la mesure où cette dimension s’étend sur la période sélectionnée.

## Renseigner cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Si une suite de rapports contient des données, cette dimension fonctionne.

## Valeurs de dimension

Les valeurs de dimension comprennent les nombres `1` - `31`, qui représentent le jour du mois où l’accès a eu lieu.
