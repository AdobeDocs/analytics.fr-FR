---
title: Heure de la journée
description: Heure numérique du jour, quel que soit le jour.
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 8%

---


# Heure de la journée

La dimension &quot;Heure du jour&quot; signale l’heure numérique d’un jour donné en tant qu’élément de dimension. Si, par exemple, vous disposez d’un rapport qui s’étend du 1er au 7 janvier, la première heure de chaque jour est regroupée dans le même élément de dimension. Ce rapport est utile si vous souhaitez qu’un rapport soit ventilé par heure relative de la journée, mais que vous ne souhaitez pas qu’une heure statique soit utilisée comme éléments de dimension. Il s’avère particulièrement utile en tant que dimension dans les rapports planifiés, dans la mesure où cette dimension s’étend sur la période sélectionnée.

Cette dimension est basée sur le fuseau horaire de la suite de rapports et non sur celui de l’visiteur local. Si, par exemple, votre suite de rapports est en heure de montagne et qu’un visiteur en Californie se rend sur votre site à 10h00, heure du Pacifique, les groupes d’accès se trouvent sous l’élément de `11:00 AM` dimension. Si vous souhaitez qu’une dimension enregistre le temps passé par l’visiteur local, l’Adobe recommande d’utiliser le plug-in [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) .

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de Dimension

Les éléments de Dimension sont `12:00 AM` - `11:00 PM`, représentant l’heure de la journée où l’accès a eu lieu (arrondie à la fin). Par exemple, si un accès a été généré à 15h58, il est regroupé sous l’élément de dimension de `3:00 PM`.

## Heure d&#39;été

L&#39;heure d&#39;été est une pratique où les horloges sont placées une heure en avance au printemps et une heure en arrière à l&#39;automne. Si le fuseau horaire d’une suite de rapports utilise l’heure d’été, l’Adobe ajuste les données en conséquence pour cette heure.

* **Début** de l&#39;heure d&#39;été : En mars, les rapports indiquent généralement un intervalle d’une heure dans les données où début l’heure d’été. L’heure n’existait pas, elle ne fait donc pas partie de la collecte de données. Notez qu’une petite quantité de données peut encore être utilisée dans cette heure. Les serveurs de collecte de données d’Adobe prennent plusieurs secondes (jusqu’à une minute) pour tenir compte des ajustements de l’heure d’été.
* **À la fin** de l’heure d’été : En novembre, les rapports indiquent généralement une heure empilée par doublon où se termine l’heure d’été. L’heure s’est produite deux fois, de sorte que les deux heures sont agrégées dans les rapports.
