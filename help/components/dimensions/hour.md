---
title: Heure
description: Heure à laquelle la mesure s’est produite.
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 12%

---


# Heure

La dimension &quot;Heure&quot; rapporte l’heure à laquelle une mesure donnée s’est produite (arrondie à la fin). Le premier élément de dimension est la première heure de la période et le dernier élément de dimension est la dernière heure de la période. Cette dimension est utile pour les rapports de tendances, car elle vous permet d’afficher les mesures au fil du temps.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de Dimension

Les éléments de Dimension incluent une heure donnée dans la plage de dates d’un rapport, ainsi que sa date. Celui-ci a la forme `HH:HH YYYY-MM-DD`.

## Heure d&#39;été

L&#39;heure d&#39;été est une pratique où les horloges sont placées une heure en avance au printemps et une heure en arrière à l&#39;automne. Si le fuseau horaire d’une suite de rapports utilise l’heure d’été, l’Adobe ajuste les données en conséquence pour cette heure.

* **Début** de l&#39;heure d&#39;été : En mars, les rapports indiquent généralement un intervalle d’une heure dans les données où début l’heure d’été. L’heure n’existait pas, elle ne fait donc pas partie de la collecte de données. Notez qu’une petite quantité de données peut encore être utilisée dans cette heure. Les serveurs de collecte de données d’Adobe prennent plusieurs secondes (jusqu’à une minute) pour tenir compte des ajustements de l’heure d’été.
* **À la fin** de l’heure d’été : En novembre, les rapports indiquent généralement une heure empilée par doublon où se termine l’heure d’été. L’heure s’est produite deux fois, de sorte que les deux heures sont agrégées dans les rapports.
