---
title: Moyenne de pages vues par visite
description: Nombre moyen de fois où un élément de dimension donné s’est affiché dans une visite.
translation-type: tm+mt
source-git-commit: 226bbce18750825d459056ac2a87549614eb3c2c
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 46%

---


# Moyenne de pages vues par visite

La dimension « Moyenne de pages vues par visite » indique le nombre moyen de pages vues en fonction de la dimension souhaitée. Pour les dimensions temporelles, vous pouvez suivre l’évolution du nombre moyen de pages vues au cours d’une visite et au fil du temps. Cette mesure s’avère utile lorsque vous souhaitez comprendre la fréquence à laquelle les éléments de dimension apparaissent au cours d’une visite.

>[!TIP]
>
>Use this metric alongside another metric (such as [Visits](visits.md)) to obtain better insights. Si vous utilisez cette mesure seule, vous obtenez des éléments de dimension contenant des vues de page irrégulières par visite, ce qui n’a généralement pas de valeur.

## Méthode de calcul de cette mesure

Cette mesure est calculée à l’aide de la formule [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Pourcentages supérieurs à 100 %

Cette mesure contient souvent des pourcentages supérieurs à 100 %. Le dénominateur correspond à la vue de page moyenne de la dimension entière par visite et le numérateur à la vue de page moyenne par visite de l’élément de dimension. Si la moyenne des vues de page par visite de la dimension entière est inférieure à la moyenne des vues de page par visite d’un élément de dimension donné, vous verrez des pourcentages supérieurs à 100 %. Le tri des rapports de classement selon cette mesure affiche une moyenne des pages vues par visite anormale, ce qui n’a généralement pas de valeur. Adobe recommande de trier selon une autre mesure, telle que [Visites](visits.md), dans les rapports de classement.