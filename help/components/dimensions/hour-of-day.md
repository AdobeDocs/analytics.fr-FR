---
title: Heure du jour
description: Heure numérique du jour, quel que soit le jour.
translation-type: tm+mt
source-git-commit: 226c54b782651ea8c6f4b7bb8030a1513c440a1d
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---


# Heure du jour

La dimension &quot;Heure du jour&quot; signale l’heure numérique d’un jour donné comme valeur de dimension. Par exemple, si un rapport s’étend du 1er au 7 janvier, la première heure de chaque jour est regroupée dans la même valeur de dimension. Ce rapport est utile si vous souhaitez qu’un rapport soit ventilé par heure relative de la journée, mais que vous ne souhaitez pas qu’une heure statique soit définie comme valeurs de dimension. Il s’avère particulièrement utile en tant que dimension dans les rapports planifiés, dans la mesure où cette dimension s’étend sur la période sélectionnée.

Cette dimension est basée sur le fuseau horaire de la suite de rapports et non sur celui de l’visiteur local. Par exemple, si votre suite de rapports est en heure de montagne et qu’un visiteur en Californie se rend sur votre site à 10h00, heure du Pacifique, les groupes d’accès se trouvent sous la valeur de `11:00 AM` dimension. Si vous souhaitez qu’une dimension enregistre le temps passé par l’visiteur local, Adobe recommande d’utiliser le plug-in [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) .

## Renseigner cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Si une suite de rapports contient des données, cette dimension fonctionne.

## Valeurs de dimension

Les valeurs de dimension comprennent `12:00 AM` - `11:00 PM`, qui représente l’heure de la journée où l’accès a eu lieu (arrondie à la fin). Par exemple, si un accès a été généré à 15h58, il est regroupé sous la valeur de dimension de `3:00 PM`.
