---
title: Durée de la visite
description: Durée de la visite pour la valeur de dimension.
translation-type: tm+mt
source-git-commit: 5282ad3f6fdd2853979cbfb2707cc07a698f63a7
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 3%

---


# Durée de la visite (secondes)

*Cette page d’aide décrit le fonctionnement de la mesure Durée de la visite. Pour plus d’informations, voir la dimension[Durée de la visite](../dimensions/time-spent-per-visit.md).*

La mesure &quot;Durée par visite (secondes)&quot; indique la durée moyenne d’interaction des visiteurs avec une valeur de dimension donnée au cours de chaque visite.

Cette mesure n’est pas disponible dans l’entrepôt de données en raison de sa structure de traitement différente.

## Méthode de calcul de cette mesure

Cette mesure utilise la formule [`Total seconds spent`](total-seconds-spent.md) ( `divided by`[`Visits`](visits.md)`minus` [`Bounces`](bounces.md)).

## Comparaison avec le temps moyen passé sur le site

Cette mesure et la durée [moyenne de consultation du site](average-time-on-site.md) sont similaires, mais présentent plusieurs différences clés. Les deux mesures utilisent &quot;Total secondes passées&quot; comme numérateur. Cependant, &quot;Durée moyenne du site&quot; utilise les séquences qui incluent un élément de dimension comme dénominateur. Le temps passé par visite utilise le décompte des visites comme dénominateur.

Par conséquent, ces mesures produisent des résultats similaires au niveau d’une visite, mais sont différentes au niveau d’un accès.

## Pourcentages supérieurs à 100 %

Cette mesure contient fréquemment des pourcentages supérieurs à 100 %. Le dénominateur correspond à la durée totale de la dimension par visite et le numérateur à la durée de chaque visite de la valeur de dimension. Si la durée totale de la visite d’une dimension est inférieure à la durée de visite d’une valeur de dimension donnée, les pourcentages s’affichent au-dessus de 100 %. Le tri des rapports avec classement selon cette mesure montre la durée d’anomalie passée par visite, ce qui n’a généralement pas de valeur. Adobe recommande le tri selon une autre mesure, telle que [Visites](visits.md), dans les rapports avec classement.

Voir Présentation [de la](time-spent.md) durée de la visite pour obtenir des informations plus générales sur la durée de la visite.
