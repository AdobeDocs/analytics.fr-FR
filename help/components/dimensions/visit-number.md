---
title: Nombre de visites
description: La énième visite du visiteur.
feature: Dimensions
exl-id: daef34b3-c270-476d-a45c-a20be6138c6b
TQID: https://experienceleague.adobe.com/C6fccfJFGSA4iLuhp2X80aPym4ZcwbrLMaUS2LUfosg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
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
source-wordcount: 164
ht-degree: 100%

---

# Nombre de visites

La [dimension](overview.md) « Nombre de visites » indique le numéro de la visite actuelle du visiteur ou de la visiteuse. Au début d’une nouvelle visite, cet élément de dimension augmente de 1. Cette dimension est utile lorsque vous souhaitez comprendre l’engagement des visiteurs lorsqu’ils reviennent sur votre site. Il s’agit d’une dimension basée sur les visites, ce qui signifie qu’elle contient la même valeur pour toute la visite et qu’elle ne peut pas être modifiée. Elle s’applique à la durée de vie du visiteur, quelle que soit la plage de dates du projet.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de dimension

Les éléments de dimension comprennent la chaîne `"Visit number"` suivie de la représentation numérique de la visite actuelle du visiteur. Par exemple, si le visiteur n’a jamais consulté votre site auparavant, sa première visite appartient à l’élément de dimension `"Visit number 1"`. S’il s’agit de la 13e visite du visiteur sur votre site, cette visite relève de l’élément de dimension `"Visit number 13"`.
