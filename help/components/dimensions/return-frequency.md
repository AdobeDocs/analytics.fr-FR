---
title: Fréquence des retours
description: Durée cumulée entre la visite en cours et la visite précédente.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '252'
ht-degree: 100%

---


# Fréquence des retours

La dimension « Fréquence des retours » indique le temps écoulé entre les visites des visiteurs réguliers. Lorsqu’un visiteur revient sur votre site, Adobe détermine la durée depuis la visite précédente et regroupe l’accès dans l’élément de dimension approprié. Cette dimension est utile pour jauger l’attrait de votre site et sa pertinence pour les visiteurs au fil du temps. Elle permet également d’identifier l’impact du contenu et des promotions de votre site sur vos visiteurs.

>[!TIP]
>
>Cette dimension n’inclut pas les nouveaux visiteurs.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

Les données de cette dimension sont définies à l’aide du premier accès de la visite et persistent pour l’ensemble de la visite. La valeur ne peut pas changer en cours de visite.

## Éléments de dimension

Les éléments de dimension comprennent des intervalles temporels, en fonction du temps écoulé depuis la visite précédente.

* Moins de 1 jour
* 1 à 3 jours
* 3 à 7 jours
* 7 à 14 jours
* 14 jours à 1 mois
* Plus d’un mois

## Éléments de dimension sous les intervalles en dehors de la période du projet

Lorsque vous définissez la période d’un projet, il est courant de voir un attribut d’élément de dimension pour les visites en dehors de la période. Par exemple, un visiteur se rend sur votre site en juillet, puis revient deux fois un même jour de septembre. La dimension « Fréquence des retours » pour le mois de septembre mentionnerait une visite sous « plus d’un mois » et une visite sous « moins d’un jour ».