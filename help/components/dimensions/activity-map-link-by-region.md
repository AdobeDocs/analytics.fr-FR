---
title: Lien d’Activity Map par région
description: Valeur concaténée de lien et de région.
feature: Dimensions
role: User, Admin
source-git-commit: 65e75a1c2b39823e72abfb0e5b61122c62f1f013
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 11%

---

# Lien d’Activity Map par région

La [dimension](overview.md) de &quot;lien Activity Map par région&quot; affiche une concaténation de [lien Activity Map](activity-map-link.md) et de [région Activity Map](activity-map-link-by-region.md). Cette dimension est utile lorsque des liens sont nommés de manière similaire, mais qu’ils résident dans différentes régions de votre site. Par exemple, si vous avez plusieurs liens vers votre page d’accueil qui sont tous intitulés &quot;Accueil&quot;, vous pouvez utiliser cette dimension pour distinguer ces liens dans chaque région du site.

## Renseigner cette dimension avec des données

Cette dimension récupère les données des [variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link` et `c.a.activitymap.region`. Ces deux valeurs sont concaténées et séparées par une barre verticale (`|`). Si votre mise en oeuvre utilise [Activity Map](/help/analyze/activity-map/overview.md), ces variables de données contextuelles collectent automatiquement des données lorsque l’utilisateur clique sur des liens.

## Éléments de dimension

Les éléments de Dimension incluent des valeurs de [Lien Activity Map](activity-map-link.md) et de [Région Activity Map](activity-map-link-by-region.md). La structure et l’implémentation du site de votre entreprise déterminent les valeurs exactes collectées.
