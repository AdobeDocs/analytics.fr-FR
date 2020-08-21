---
title: Fréquence des retours
description: Durée cumulée entre la visite en cours et la visite précédente.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 71%

---


# Fréquence des retours

La dimension « Fréquence des retours » indique le temps écoulé entre les visites des visiteurs réguliers. Lorsqu’un visiteur revient sur votre site, l’Adobe examine depuis combien de temps se trouvait la visite précédente et regroupe l’accès dans l’élément de dimension approprié. Cette dimension est utile pour jauger l’attrait de votre site et sa pertinence pour les visiteurs au fil du temps. Elle permet également d’identifier l’impact du contenu et des promotions de votre site sur vos visiteurs.

>[!TIP]
>
>Cette dimension n’inclut pas les nouveaux visiteurs.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

Les données de cette dimension sont définies à l’aide du premier accès de la visite et persistent pour l’ensemble de la visite. La valeur ne peut pas changer en cours de visite.

## Éléments de Dimension

Les éléments de Dimension incluent des intervalles temporels, en fonction du temps écoulé depuis la visite précédente.

* Moins de 1 jour
* 1 à 3 jours
* 3 à 7 jours
* 7 à 14 jours
* 14 jours à 1 mois
* Plus d’un mois

## Les éléments de Dimension apparaissent sous des intervalles en dehors de la plage de dates du projet.

Lorsque vous définissez la plage de dates d’un projet, il est courant de voir l’attribut des éléments de dimension pour les visites en dehors de la plage de dates. Par exemple, un visiteur se rend sur votre site en juillet, puis revient deux fois un même jour de septembre. La dimension « Fréquence des retours » pour le mois de septembre mentionnerait une visite sous « plus d’un mois » et une visite sous « moins d’un jour ».