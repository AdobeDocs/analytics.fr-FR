---
title: Fréquence des retours
description: Durée cumulée entre la visite en cours et la visite précédente.
feature: Dimensions
exl-id: 8ec31e17-a57d-416f-b471-c2c37a98d134
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 93%

---

# Fréquence des retours

La [dimension](overview.md) de &quot;Fréquence des retours&quot; indique la durée qui s’écoule entre les visites des visiteurs récurrents. Lorsqu’un visiteur revient sur votre site, Adobe détermine la durée depuis la visite précédente et regroupe l’accès dans l’élément de dimension approprié. Cette dimension est utile pour jauger l’attrait de votre site et sa pertinence pour les visiteurs au fil du temps. Elle permet également d’identifier l’impact du contenu et des promotions de votre site sur vos visiteurs.

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
