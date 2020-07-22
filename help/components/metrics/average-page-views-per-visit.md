---
title: vues moyennes de page par visite
description: Nombre moyen de fois où un élément de dimension donné s’est affiché dans une visite.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---


# vues moyennes de page par visite

La dimension &quot;vues moyennes de page par visite&quot; indique le nombre moyen de vues de page survenues par rapport à la dimension souhaitée. Pour les dimensions temporelles, vous pouvez voir comment le nombre moyen de vues de page au cours d’une visite évolue au fil du temps. Cette mesure s’avère utile lorsque vous souhaitez comprendre la fréquence à laquelle les éléments de dimension apparaissent au cours d’une visite.

>[CONSEIL] Utilisez cette mesure en même temps qu’une autre mesure ( [Visites](visits.md), par exemple) pour obtenir de meilleures informations. Si vous utilisez cette mesure seule, vous obtenez des éléments de dimension contenant des vues de page irrégulières par visite, ce qui n’a généralement pas de valeur.

## Méthode de calcul de cette mesure

Cette mesure est calculée à l’aide de la formule [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Pourcentages supérieurs à 100 %

Cette mesure contient fréquemment des pourcentages supérieurs à 100 %. Le dénominateur correspond à la vue de page moyenne de la dimension entière par visite et le numérateur à la vue de page moyenne par visite de l’élément de dimension. Si la moyenne des vues de page par visite de la dimension entière est inférieure à la moyenne des vues de page par visite d’un élément de dimension donné, vous verrez des pourcentages supérieurs à 100 %. Le tri des rapports avec classement selon cette mesure montre les vues de page moyennes irrégulières par visite, ce qui n’a généralement pas de valeur. Adobe recommande le tri selon une autre mesure, telle que [Visites](visits.md), dans les rapports avec classement.