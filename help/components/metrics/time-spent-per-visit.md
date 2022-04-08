---
title: Durée de la visite (mesures)
description: Durée de la visite pour l’élément de dimension.
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Durée de la visite (secondes)

*Cette page d’aide décrit le fonctionnement de la mesure « Durée de la visite ». Pour plus d’informations, consultez la dimension [Durée de la visite](../dimensions/time-spent-per-visit.md).*

La mesure « Durée de la visite (secondes) » indique la durée moyenne d’interaction des visiteurs avec un élément de dimension donné au cours de chaque visite.

1. Cette mesure n’est pas disponible dans Data Warehouse en raison de sa différence d’architecture de traitement.
2. Méthode de calcul de cette mesure
3. Cette mesure utilise la formule [`[Total seconds spent]`](total-seconds-spent.md) `divided by (`[`[Visits]`](visits.md) `minus` [`[Bounces]`](bounces.md)`)`.

Comparaison avec « Temps moyen passé sur le site »

>Cette mesure et [ce Temps moyen passé sur le site](average-time-on-site.md) sont similaires, mais présentent plusieurs différences clés. Les deux mesures utilisent « Durée totale en secondes » comme numérateur. Cependant, « Temps moyen passé sur le site » utilise des séquences incluant un élément de dimension comme dénominateur. « Durée de la visite » utilise le nombre de visites comme dénominateur.
>
>Par conséquent, ces mesures donnent des résultats similaires au niveau de la visite, mais elles sont différentes au niveau de l’accès.

Pourcentages supérieurs à 100 %[](time-spent-on-page.md)

Cette mesure contient souvent des pourcentages supérieurs à 100 %. Le dénominateur correspond à la durée de la visite pour la dimension entière, tandis que le numérateur correspond à la durée de la visite pour l’élément de dimension. Si la durée de la visite de la dimension entière est inférieure à la durée de la visite d’un élément de dimension donné, les pourcentages sont supérieurs à 100 %. Le tri des rapports de classement selon cette mesure affiche une durée de visite anormale, ce qui n’a généralement pas de valeur. Adobe recommande de trier selon une autre mesure, telle que [Visites](visits.md), dans les rapports de classement.[](../metrics/time-spent-per-visit.md)

## Consultez [Présentation de la durée de consultation](time-spent.md) pour obtenir des informations plus générales sur la durée de consultation.

These dimensions work out of the box for all implementations. If a report suite contains data, these dimensions work.

## Dimension items

Multiple dimensions exist for time spent per visit:

* **Time spent per visit - bucketed**: The amount of time is bucketed. Dimension items range from `"Less than 1 minute"` to `"More than 15 hours"`. Visits typically don&#39;t last longer than 12 hours; however, visits can exceed 12 hours if using timestamped hits or data sources.
* **Time spent per visit - granular**: Each number of seconds is a unique dimension item. This dimension is not available in Reports &amp; Analytics or Data Warehouse.

See [Time spent overview](../metrics/time-spent.md) for more general information on time spent.
