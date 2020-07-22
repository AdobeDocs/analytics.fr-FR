---
title: Durée de la visite
description: Durée de la visite pour l’élément de dimension.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 3%

---


# Durée de la visite (secondes)

*Cette page d’aide décrit le fonctionnement de la mesure Durée de la visite. Pour plus d’informations, voir la dimension[Durée de la visite](../dimensions/time-spent-per-visit.md).*

La mesure Durée par visite (secondes) indique la durée moyenne d’interaction des visiteurs avec un élément de dimension donné lors de chaque visite.

Cette mesure n’est pas disponible dans le Data warehouse en raison de sa différence d’architecture de traitement.

## Méthode de calcul de cette mesure

Cette mesure utilise la formule [`Total seconds spent`](total-seconds-spent.md) ( `divided by`[`Visits`](visits.md)`minus` [`Bounces`](bounces.md)).

## Comparaison avec le temps moyen passé sur le site

Cette mesure et la durée [moyenne de consultation du site](average-time-on-site.md) sont similaires, mais présentent plusieurs différences clés. Les deux mesures utilisent &quot;Total secondes passées&quot; comme numérateur. Cependant, &quot;Durée moyenne du site&quot; utilise les séquences qui incluent un élément de dimension comme dénominateur. Le temps passé par visite utilise le décompte des visites comme dénominateur.

Par conséquent, ces mesures produisent des résultats similaires au niveau d’une visite, mais sont différentes au niveau d’un accès.

## Pourcentages supérieurs à 100 %

Cette mesure contient fréquemment des pourcentages supérieurs à 100 %. Le dénominateur correspond à la durée totale de la dimension par visite et le numérateur à la durée de visite de l’élément de dimension. Si la durée totale de la visite d’une dimension est inférieure à la durée de visite d’un élément de dimension donné, les pourcentages s’affichent au-dessus de 100 %. Le tri des rapports avec classement selon cette mesure montre la durée d’anomalie passée par visite, ce qui n’a généralement pas de valeur. Adobe recommande le tri selon une autre mesure, telle que [Visites](visits.md), dans les rapports avec classement.

Voir Présentation [de la](time-spent.md) durée de la visite pour obtenir des informations plus générales sur la durée de la visite.
