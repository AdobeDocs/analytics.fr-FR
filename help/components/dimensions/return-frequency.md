---
title: Fréquence des retours
description: Durée cumulée entre la visite en cours et la visite précédente.
feature: Dimensions
exl-id: 8ec31e17-a57d-416f-b471-c2c37a98d134
TQID: https://experienceleague.adobe.com/k0H7kOCgrBRY3cZckPXaJ9UgLBPTYWHxKT8gzeMQjcI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 267
ht-degree: 94%

---

# Fréquence des retours

La [dimension](overview.md) « Fréquence des retours » indique le temps écoulé entre les visites des visiteurs récurrents. Lorsqu’un visiteur revient sur votre site, Adobe détermine la durée depuis la visite précédente et regroupe l’accès dans l’élément de dimension approprié. Cette dimension est utile pour jauger l’attrait de votre site et sa pertinence pour les visiteurs au fil du temps. Elle permet également d’identifier l’impact du contenu et des promotions de votre site sur vos visiteurs.

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
