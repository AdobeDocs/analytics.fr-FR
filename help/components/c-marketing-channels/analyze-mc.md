---
title: Analyse des canaux marketing
description: Découvrez comment utiliser les dimensions des canaux marketing dans Workspace.
exl-id: 7030e41a-4e92-45c7-9725-66a3ef019313
translation-type: tm+mt
source-git-commit: 7202a49dda7c3ef4f4b535476d3cf637b9e9f7f6
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 81%

---

# Analyse des canaux marketing

>[!NOTE]
>
>Pour optimiser l&#39;efficacité des Canaux marketing pour l&#39;Attribution IQ et le Customer Journey Analytics, nous avons publié quelques [meilleures pratiques révisées](/help/components/c-marketing-channels/mchannel-best-practices.md).

Vous souhaitez probablement savoir lequel de vos canaux marketing est le plus efficace et avec qui, afin de mieux cibler vos efforts et de bénéficier d’un meilleur retour sur votre investissement en marketing. Dans Adobe Analytics, les dimensions et les mesures des canaux marketing de Workspace sont l’un des outils qui peuvent vous aider à suivre l’influence de différents canaux sur vos commandes, recettes, etc. et vous donner des informations utiles sur les canaux. Voici les dimensions et les mesures que vous pouvez utiliser en lien avec les canaux marketing :

![](assets/mc-dims.png)

| Dimension/Mesure | Définition |
| --- | --- |
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

## Analyse marketing entre onglets

En utilisant l’ancien Canal Première touche et le Canal Dernière touche, vous pouvez obtenir une vue utile sur les interactions canal :

![](assets/mc-viz6.png)

Pour en savoir plus sur l’analyse marketing par onglets croisés, consultez cette vidéo : [Utilisation de l’Analyse à onglets croisés pour explorer l’attribution de base du marketing dans Analysis Workspace](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-cross-tab-analysis-to-explore-basic-marketing-attribution-in-analysis-workspace.html).
