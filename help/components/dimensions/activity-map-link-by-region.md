---
title: Lien d’Activity Map par région
description: Valeur concaténée de lien et de région.
feature: Dimensions
role: User, Admin
exl-id: 33014dc1-da4e-47b7-b73c-3e89e04f3ed6
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 11%

---

# Lien d’Activity Map par région

La [dimension](overview.md) « Lien Activity Map par région » affiche une concaténation de [Lien Activity Map](activity-map-link.md) et [Région Activity Map](activity-map-link-by-region.md). Cette dimension est utile lorsque vous disposez de liens dont le nom est similaire, mais qui résident dans différentes régions de votre site. Par exemple, si votre page d’accueil comporte plusieurs liens intitulés tous « Accueil », vous pouvez utiliser cette dimension pour distinguer ces liens dans chaque zone géographique du site.

## Renseigner cette dimension avec des données

Cette dimension récupère les données des [ et ](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`Variables de données contextuelles`c.a.activitymap.region`. Ces deux valeurs sont concaténées et séparées par une barre verticale (`|`). Si votre implémentation utilise [Activity Map](/help/analyze/activity-map/overview.md), ces variables de données contextuelles collectent automatiquement les données lorsque l’utilisateur clique sur les liens.

## Éléments de dimension

Les éléments Dimension incluent les valeurs de [Activity Map Link](activity-map-link.md) et [Activity Map Region](activity-map-link-by-region.md). La structure et l’implémentation du site de votre entreprise déterminent les valeurs exactes collectées.
