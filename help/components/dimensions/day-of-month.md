---
title: Jour du mois
description: Jour numérique du mois, quel que soit le mois.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 4%

---


# Jour du mois

La dimension &quot;Jour du mois&quot; signale le jour numérique d’un mois donné en tant qu’élément de dimension. Si, par exemple, vous disposez d’un rapport couvrant la période du 1er janvier au 31 mars, le premier de chaque mois est regroupé dans le même élément de dimension. Ce rapport est utile si vous souhaitez qu’un rapport soit ventilé par jour, mais que vous ne souhaitez pas qu’une date statique soit considérée comme des éléments de dimension. Il s’avère particulièrement utile en tant que dimension dans les rapports planifiés, dans la mesure où cette dimension s’étend sur la période sélectionnée.

## Renseigner cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Si une suite de rapports contient des données, cette dimension fonctionne.

## Éléments de dimension

Les éléments de dimension comprennent les nombres `1` - `31`, qui représentent le jour du mois où l’accès a eu lieu.
