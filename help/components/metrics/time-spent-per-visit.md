---
title: Durée par visite (mesures)
description: Durée de la visite pour l’élément de dimension.
feature: Metrics
exl-id: 0f951196-66a2-4733-bb62-4555a9331efb
TQID: https://experienceleague.adobe.com/X1RtHTTmu0VIblFC3jANE7d6bIbtm4W5OvqFZDp8bLE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 263
ht-degree: 88%

---

# Durée de la visite (secondes)

*Cette page d’aide décrit le fonctionnement de la mesure « Durée de la visite ». Pour plus d’informations, consultez la dimension [Durée de la visite](../dimensions/time-spent-per-visit.md).*

La mesure « Durée par visite (secondes) » [s](overview.md) indique la durée moyenne pendant laquelle les visiteurs et visiteuses interagissent avec un élément de dimension donné au cours de chaque visite.

Cette mesure n’est pas disponible dans Data Warehouse en raison de sa différence d’architecture de traitement.

## Méthode de calcul de cette mesure

Cette mesure utilise la formule [`[Total seconds spent]`](total-seconds-spent.md) `divided by (`[`[Visits]`](visits.md) `minus` [`[Bounces]`](bounces.md)`)`.

## Comparaison avec « Temps moyen passé sur le site »

Cette mesure et [ce Temps moyen passé sur le site](average-time-on-site.md) sont similaires, mais présentent plusieurs différences clés. Les deux mesures utilisent « Durée totale en secondes » comme numérateur. Cependant, « Temps moyen passé sur le site » utilise des séquences incluant un élément de dimension comme dénominateur. « Durée de la visite » utilise le nombre de visites comme dénominateur.

Par conséquent, ces mesures donnent des résultats similaires au niveau de la visite, mais elles sont différentes au niveau de l’accès.

## Pourcentages supérieurs à 100 %

Cette mesure contient souvent des pourcentages supérieurs à 100 %. Le dénominateur correspond à la durée de la visite pour la dimension entière, tandis que le numérateur correspond à la durée de la visite pour l’élément de dimension. Si la durée de la visite de la dimension entière est inférieure à la durée de la visite d’un élément de dimension donné, les pourcentages sont supérieurs à 100 %. Le tri des rapports de classement selon cette mesure affiche une durée de visite anormale, ce qui n’a généralement pas de valeur. Adobe recommande de trier selon une autre mesure, telle que [Visites](visits.md), dans les rapports de classement.

Consultez [Présentation de la durée de consultation](time-spent.md) pour obtenir des informations plus générales sur la durée de consultation.
