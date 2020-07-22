---
title: Durée par visiteur (secondes)
description: null
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 6%

---


# Durée par visiteur (secondes)

La mesure &quot;Durée de consultation par visiteur (secondes)&quot; indique la durée moyenne d’interaction des visiteurs avec un élément de dimension donné pendant toute la durée de vie d’un visiteur.

Cette mesure n’est pas disponible dans le Data warehouse en raison de sa différence d’architecture de traitement.

## Méthode de calcul de cette mesure

Cette mesure utilise la formule [`Total seconds spent`](total-seconds-spent.md)`divided by` [`Unique visitors`](unique-visitors.md).

## Pourcentages supérieurs à 100 %

Cette mesure contient fréquemment des pourcentages supérieurs à 100 %. Le dénominateur est la durée totale de la dimension par visiteur et le numérateur est la durée de l’élément de dimension par visiteur. Si la durée totale de la dimension par visiteur est inférieure à la durée passée par un élément de dimension donné par visiteur, vous verrez des pourcentages supérieurs à 100 %. Le tri des rapports avec classement selon cette mesure montre la durée d’anomalie passée par valeur de visiteur, qui n’a généralement pas de valeur. Adobe recommande le tri selon une autre mesure, telle que [Visites](visits.md), dans les rapports avec classement.

Voir Présentation [de la](time-spent.md) durée de la visite pour obtenir des informations plus générales sur la durée de la visite.
