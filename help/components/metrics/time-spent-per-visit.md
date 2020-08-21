---
title: Durée de la visite
description: Durée de la visite pour l’élément de dimension.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 69%

---


# Durée de la visite (secondes)

*Cette page d’aide décrit le fonctionnement de la mesure « Durée de la visite ». Pour plus d’informations, consultez la dimension[Durée de la visite](../dimensions/time-spent-per-visit.md).*

La mesure Durée par visite (secondes) indique la durée moyenne d’interaction des visiteurs avec un élément de dimension donné lors de chaque visite.

Cette mesure n’est pas disponible dans Data Warehouse en raison de sa différence d’architecture de traitement.

## Méthode de calcul de cette mesure

Cette mesure utilise la formule [`Total seconds spent`](total-seconds-spent.md) `divided by` ([`Visits`](visits.md) `minus` [`Bounces`](bounces.md)).

## Comparaison avec « Temps moyen passé sur le site »

Cette mesure et [ce Temps moyen passé sur le site](average-time-on-site.md) sont similaires, mais présentent plusieurs différences clés. Les deux mesures utilisent « Durée totale en secondes » comme numérateur. Cependant, « Temps moyen passé sur le site » utilise des séquences incluant un élément de dimension comme dénominateur. « Durée de la visite » utilise le nombre de visites comme dénominateur.

Par conséquent, ces mesures donnent des résultats similaires au niveau de la visite, mais elles sont différentes au niveau de l’accès.

## Pourcentages supérieurs à 100 %

Cette mesure contient souvent des pourcentages supérieurs à 100 %. Le dénominateur correspond à la durée totale de la dimension par visite et le numérateur à la durée de visite de l’élément de dimension. Si la durée totale de la visite d’une dimension est inférieure à la durée de visite d’un élément de dimension donné, les pourcentages s’affichent au-dessus de 100 %. Le tri des rapports de classement selon cette mesure affiche une durée de visite anormale, ce qui n’a généralement pas de valeur. Adobe recommande de trier selon une autre mesure, telle que [Visites](visits.md), dans les rapports de classement.

Consultez [Présentation de la durée de consultation](time-spent.md) pour obtenir des informations plus générales sur la durée de consultation.
