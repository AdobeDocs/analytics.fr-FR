---
title: Heure de la journée
description: Heure numérique de la journée, indépendamment du jour.
feature: Dimensions
exl-id: b9361534-7e58-41ed-9a38-c02aeed7a2d8
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 95%

---

# Heure de la journée

La [dimension](overview.md) &quot;Heure de la journée&quot; indique l’heure numérique d’un jour donné comme élément de dimension. Par exemple, si vous disposez d’un rapport qui s’étend du 1er au 7 janvier, la première heure de chaque jour est regroupée dans le même élément de dimension. Ce rapport est utile si vous souhaitez un rapport divisé par heure de la journée, mais ne souhaitez pas d’heures statiques comme éléments de dimension. Il s’avère particulièrement utile comme dimension dans les rapports planifiés, dans la mesure où cette dimension s’étend sur la période sélectionnée.

Cette dimension est basée sur le fuseau horaire de la suite de rapports, et non sur celui du visiteur. Par exemple, si votre suite de rapports est à l’heure des Rocheuses et qu’un visiteur en Californie se rend sur votre site à 10 h (heure du Pacifique), les groupes d’accès se trouvent sous l’élément de dimension `11:00 AM`. Si vous souhaitez une dimension qui enregistre l’heure locale du visiteur, Adobe recommande d’utiliser le plug-in [getTimeParting](/help/implement/vars/plugins/gettimeparting.md).

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de dimension

Les éléments de dimension vont de `12:00 AM` à `11:00 PM`, ce qui représente l’heure de la journée où l’accès a eu lieu (arrondie à l’unité inférieure). Par exemple, si un accès a été généré à 15 h 58, il est regroupé sous l’élément de dimension `3:00 PM`.

## Heure d’été

L’heure d’été est une pratique qui consiste à avancer les horloges d’une heure au printemps et à les reculer d’une heure à l’automne. Si le fuseau horaire d’une suite de rapports utilise l’heure d’été, Adobe adapte les données en fonction de cette heure.

* **Début de l’heure d’été** : en mars, les rapports indiquent généralement un décalage d’une heure dans les données au début de l’heure d’été. L’heure n’existe pas, elle ne fait donc pas partie de la collecte de données. Notez qu’une petite quantité de données peut encore se trouver dans cette heure. Les serveurs de collecte de données d’Adobe prennent plusieurs secondes (jusqu’à une minute) pour tenir compte des ajustements à l’heure d’été.
* **Fin de l’heure d’été** : en novembre, les rapports indiquent généralement une heure doublée à la fin de l’heure d’été. L’heure apparaissant deux fois, les deux heures sont agrégées dans les rapports.
