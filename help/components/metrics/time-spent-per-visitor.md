---
title: Durée par visiteur (secondes)
description: null
translation-type: tm+mt
source-git-commit: 5282ad3f6fdd2853979cbfb2707cc07a698f63a7
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 6%

---


# Durée par visiteur (secondes)

La mesure &quot;Durée par visiteur (secondes)&quot; indique la durée moyenne d’interaction des visiteurs avec une valeur de dimension donnée au cours de la vie entière d’un visiteur.

Cette mesure n’est pas disponible dans l’entrepôt de données en raison de sa structure de traitement différente.

## Méthode de calcul de cette mesure

Cette mesure utilise la formule [`Total seconds spent`](total-seconds-spent.md)`divided by` [`Unique visitors`](unique-visitors.md).

## Pourcentages supérieurs à 100 %

Cette mesure contient fréquemment des pourcentages supérieurs à 100 %. Le dénominateur correspond à la durée totale de la dimension par visiteur et le numérateur à la durée de la dimension par visiteur. Si la durée totale de la dimension par visiteur est inférieure à la durée passée par visiteur par une valeur de dimension donnée, les pourcentages s’afficheront au-dessus de 100 %. Le tri des rapports avec classement selon cette mesure montre la durée d’anomalie passée par valeur de visiteur, qui n’a généralement pas de valeur. Adobe recommande le tri selon une autre mesure, telle que [Visites](visits.md), dans les rapports avec classement.

Voir Présentation [de la](time-spent.md) durée de la visite pour obtenir des informations plus générales sur la durée de la visite.
