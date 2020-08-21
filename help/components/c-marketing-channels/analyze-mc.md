---
title: Analyse des canaux marketing
description: Découvrez comment utiliser les dimensions des canaux marketing dans Workspace.
translation-type: ht
source-git-commit: 586dabe8454bb2e6fbd4f3fbdb18d13a18b0417d
workflow-type: ht
source-wordcount: '407'
ht-degree: 100%

---


# Analyse des canaux marketing

Vous souhaitez probablement savoir lequel de vos canaux marketing est le plus efficace et avec qui, afin de mieux cibler vos efforts et de bénéficier d’un meilleur retour sur votre investissement en marketing. Dans Adobe Analytics, les dimensions et les mesures des canaux marketing de Workspace sont l’un des outils qui peuvent vous aider à suivre l’influence de différents canaux sur vos commandes, recettes, etc. et vous donner des informations utiles sur les canaux. Voici les dimensions et les mesures que vous pouvez utiliser en lien avec les canaux marketing :

![](assets/mc-dims.png)

| Dimension/Mesure | Définition |
|---|---|
| Canal marketing | Il s’agit de la dimension Canaux marketing recommandée. Les modèles Attribution IQ peuvent être appliqués à celui-ci au moment de l’exécution. Cette dimension se comporte de la même manière que la dimension Canal Dernière touche, mais elle est étiquetée différemment pour éviter toute confusion lors de son utilisation avec un modèle d’attribution différent. |
| Canal Dernière touche | Dimension héritée, avec modèle d’attribution Dernière touche préappliqué et non modifiable. |
| Canal Première touche | Dimension héritée, avec modèle d’attribution Première touche préappliqué et non modifiable. |
| Instances de canaux marketing | Cette mesure calcule le nombre de fois où un canal marketing a été défini dans une demande d’image, y compris les pages vues standards et les appels de liens personnalisés. N’inclut pas les valeurs persistantes. |
| Nouveaux engagements | Cette mesure est similaire aux instances, mais elle n’est incrémentée que lorsque le canal marketing Première touche est défini dans une demande d’image. |

## Analyse de base

Ce tableau à structure libre présente les mesures Commandes en ligne, Recettes en ligne et Taux de conversion pour chacun des Canaux marketing :

![](assets/mc-viz1.png)

Vous voyez ici chaque mesure Commandes en ligne et Recettes en ligne par Canal marketing dans un graphique en anneau :

![](assets/mc-viz2.png)

Ce graphique en courbes présente les tendances des Commandes en ligne pour divers canaux au fil du temps :

![](assets/mc-viz3.png)

## Analyse avancée

Détail des canaux marketing permet d’approfondir les analyses de chaque canal pour vous montrer des campagnes ou des emplacements spécifiques par exemple. Vous pouvez ventiler chaque Canal marketing en détails :

![](assets/mc-viz4.png)

## Application des modèles d’attribution

Vous pouvez utiliser [Attribution IQ](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/panels/attribution.html) pour appliquer instantanément différents modèles d’attribution :

![](assets/mc-viz5.png)

Notez comment une même mesure (Commandes en ligne) génère des résultats différents lorsque vous appliquez différents modèles d’attribution.

Voici quelques vidéos expliquant en détail Attribution IQ : [Playlist Attribution IQ](https://www.youtube.com/playlist?list=PL2tCx83mn7GuDzYEZ8jQlaScruZr3tBTR).

## Analyse marketing entre onglets

En utilisant le Canal Première touche et le Canal Dernière touche hérités, vous pouvez obtenir des informations utiles sur les interactions de canal :

![](assets/mc-viz6.png)

Pour en savoir plus sur les analyses entre onglets, consultez [cette vidéo](https://www.youtube.com/watch?v=M3EOdONa-3E).
