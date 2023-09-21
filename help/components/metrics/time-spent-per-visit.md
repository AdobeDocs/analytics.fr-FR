---
title: Durée de la visite (mesures)
description: Durée de la visite pour l’élément de dimension.
feature: Metrics
exl-id: 0f951196-66a2-4733-bb62-4555a9331efb
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 88%

---

# Durée de la visite (secondes)

*Cette page d’aide décrit le fonctionnement de la mesure « Durée de la visite ». Pour plus d’informations, consultez la dimension [Durée de la visite](../dimensions/time-spent-per-visit.md).*

&quot;Durée de la visite (secondes)&quot; [metric](overview.md) indique la durée moyenne d’interaction des visiteurs avec un élément de dimension donné au cours de chaque visite.

Cette mesure n’est pas disponible dans Data Warehouse en raison de sa différence d’architecture de traitement.

## Méthode de calcul de cette mesure

Cette mesure utilise la formule [`[Total seconds spent]`](total-seconds-spent.md) `divided by (`[`[Visits]`](visits.md) `minus` [`[Bounces]`](bounces.md)`)`.

## Comparaison avec « Temps moyen passé sur le site »

Cette mesure et [ce Temps moyen passé sur le site](average-time-on-site.md) sont similaires, mais présentent plusieurs différences clés. Les deux mesures utilisent « Durée totale en secondes » comme numérateur. Cependant, « Temps moyen passé sur le site » utilise des séquences incluant un élément de dimension comme dénominateur. « Durée de la visite » utilise le nombre de visites comme dénominateur.

Par conséquent, ces mesures donnent des résultats similaires au niveau de la visite, mais elles sont différentes au niveau de l’accès.

## Pourcentages supérieurs à 100 %

Cette mesure contient souvent des pourcentages supérieurs à 100 %. Le dénominateur correspond à la durée de la visite pour la dimension entière, tandis que le numérateur correspond à la durée de la visite pour l’élément de dimension. Si la durée de la visite de la dimension entière est inférieure à la durée de la visite d’un élément de dimension donné, les pourcentages sont supérieurs à 100 %. Le tri des rapports de classement selon cette mesure affiche une durée de visite anormale, ce qui n’a généralement pas de valeur. Adobe recommande de trier selon une autre mesure, telle que [Visites](visits.md), dans les rapports de classement.

Consultez [Présentation de la durée de consultation](time-spent.md) pour obtenir des informations plus générales sur la durée de consultation.
