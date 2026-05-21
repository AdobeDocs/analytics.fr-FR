---
title: Lien d’Activity Map par région
description: Valeur concaténée de lien et de région.
feature: Dimensions
role: User, Admin
exl-id: 33014dc1-da4e-47b7-b73c-3e89e04f3ed6
TQID: https://experienceleague.adobe.com/xvYVA064hA0rsBdnLpxXllq3PD0zYAikFRjc6xNErvg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 151
ht-degree: 11%

---

# Lien d’Activity Map par région

La [dimension](overview.md) « Lien Activity Map par région » affiche une concaténation de [Lien Activity Map](activity-map-link.md) et [Région Activity Map](activity-map-link-by-region.md). Cette dimension est utile lorsque vous disposez de liens dont le nom est similaire, mais qui résident dans différentes régions de votre site. Par exemple, si votre page d’accueil comporte plusieurs liens intitulés tous « Accueil », vous pouvez utiliser cette dimension pour distinguer ces liens dans chaque zone géographique du site.

## Renseigner cette dimension avec des données

Cette dimension récupère les données des `c.a.activitymap.link` et `c.a.activitymap.region` [Variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md). Ces deux valeurs sont concaténées et séparées par une barre verticale (`|`). Si votre implémentation utilise [&#128279;](/help/analyze/activity-map/overview.md), ces variables de données contextuelles collectent automatiquement les données lorsque l’utilisateur clique sur les liens.

## Éléments de dimension

Les éléments Dimension incluent les valeurs de [Activity Map Link](activity-map-link.md) et [Activity Map Region](activity-map-link-by-region.md). La structure et l’implémentation du site de votre entreprise déterminent les valeurs exactes collectées.
