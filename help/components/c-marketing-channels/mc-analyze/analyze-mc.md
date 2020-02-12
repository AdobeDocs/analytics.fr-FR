---
title: Analyse des canaux marketing
description: Découvrez comment utiliser les dimensions Canaux marketing dans Workspace.
translation-type: tm+mt
source-git-commit: 53a4f2cf78077a81d888401777323f5543cfc71c

---


# Analyse des canaux marketing

Vous souhaitez probablement savoir quels sont vos canaux marketing les plus efficaces et avec qui, afin de mieux cibler vos efforts et de bénéficier d’un meilleur retour sur vos investissements marketing. Dans Adobe Analytics, les dimensions et les mesures des canaux marketing dans Workspace sont l’un des outils qui peuvent vous aider à suivre l’influence des différents canaux sur vos commandes, recettes, etc. et vous donner des informations utiles sur les canaux. Voici les dimensions et les mesures que vous pouvez utiliser en rapport avec les canaux marketing :

![](assets/mc-dims.png)

| Dimension/Mesure | Définition |
|---|---|
| Canal marketing | Il s’agit de la dimension Canaux marketing que nous vous recommandons d’utiliser. Les modèles de QI d’attribution peuvent être appliqués à celui-ci au moment de l’exécution. La dimension Canaux marketing génériques se comporte de la même manière que les dimensions Canal Dernière touche, mais elle est étiquetée différemment pour éviter toute confusion lors de son utilisation avec un modèle d’attribution différent. |
| Canal Dernière touche | Dimension héritée, avec modèle d’attribution préappliqué et inmodifiable. |
| Canal Première touche | Dimension héritée, avec modèle d’attribution préappliqué et inmodifiable. |
| [Instances de canal marketingCette mesure...] |
| Nouveaux engagements | Il s’agit d’une mesure héritée qui est incrémentée uniquement lorsqu’une allocation Première touche est appliquée à un canal. |

## Analyse de base

Ce tableau à structure libre présente les mesures Commandes en ligne, Recettes en ligne et Taux de conversion pour chacun des canaux marketing :

![](assets/mc-viz1.png)

Vous voyez ici les commandes en ligne et les recettes en ligne de chaque canal marketing dans un graphique en anneau :

![](assets/mc-viz2.png)

Ce graphique en courbes présente les tendances des commandes en ligne pour divers canaux au fil du temps :

![](assets/mc-viz3.png)

## Analyse avancée

Détails des canaux marketing approfondissent l’analyse de chaque canal pour vous montrer des campagnes, des emplacements, etc. spécifiques. Vous pouvez ventiler chaque canal marketing en détails :

![](assets/mc-viz4.png)

## Appliquer des modèles d’attribution

Vous pouvez utiliser le QI [](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/use-attribution.html) d’attribution pour appliquer différents modèles d’attribution instantanément :

![](assets/mc-viz5.png)

Notez comment la même mesure (Commandes en ligne) génère des résultats différents lorsque vous appliquez différents modèles d’attribution.

Voici quelques vidéos expliquant en détail l’QI d’attribution : Liste de lecture [de QI d’attribution](https://www.youtube.com/playlist?list=PL2tCx83mn7GuDzYEZ8jQlaScruZr3tBTR).

## Analyse marketing par onglets croisés

Grâce au canal Première touche et au canal Dernière touche hérités, vous obtenez une vue d’ensemble utile sur les interactions des canaux :

![](assets/mc-viz6.png)

En savoir plus sur [cette vidéo](https://www.youtube.com/watch?v=M3EOdONa-3E).