---
title: Analyse des canaux marketing
description: Découvrez comment utiliser les dimensions des canaux marketing dans Workspace.
feature: Marketing Channels
exl-id: 7030e41a-4e92-45c7-9725-66a3ef019313
TQID: https://experienceleague.adobe.com/XWjRuwOusH-TsOb5rzG8rAIkye3faYxfZzyQOMrav3Q
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 435
ht-degree: 77%

---

# Analyse des canaux marketing

>[!NOTE]
>
>Afin d’optimiser l’efficacité des canaux marketing pour l’attribution et Adobe Analytics, nous avons publié quelques [bonnes pratiques révisées](/help/components/c-marketing-channels/mchannel-best-practices.md).
>
>Les administrateurs et administratrices d’Analytics peuvent gérer les canaux marketing pour leurs organisations, comme décrit dans la section [Gestion des canaux marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).

Vous souhaitez probablement savoir lequel de vos canaux marketing est le plus efficace et avec qui, afin de mieux cibler vos efforts et de bénéficier d’un meilleur retour sur votre investissement en marketing. Dans Adobe Analytics, les dimensions et mesures Canaux marketing de Workspace sont l’un des outils qui peuvent vous aider à suivre l’influence de différents canaux sur vos commandes, votre chiffre d’affaires, etc. et à obtenir des informations utiles sur les canaux. Voici les dimensions et les mesures que vous pouvez utiliser en lien avec les canaux marketing :

![](assets/mc-dims.png)

| Dimension/Mesure | Définition |
| --- | --- |
| Canal marketing | Il s’agit de la dimension Canaux marketing recommandée. Les modèles d’attribution peuvent lui être appliqués au moment de l’exécution. Cette dimension se comporte de la même manière que la dimension Canal Dernière touche, mais elle est étiquetée différemment pour éviter toute confusion lors de son utilisation avec un modèle d’attribution différent. |
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

Détails sur les canaux marketing examine plus en détail chaque canal afin de vous présenter des campagnes, des emplacements, etc. spécifiques. Vous pouvez ventiler chaque canal marketing en détails :

![](assets/mc-viz4.png)

## Application des modèles d’attribution

Vous pouvez utiliser [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) pour appliquer instantanément différents modèles d’attribution :

![](assets/mc-viz5.png)

Notez comment une même mesure (Commandes en ligne) génère des résultats différents lorsque vous appliquez différents modèles d’attribution.

## Analyse marketing entre onglets

En utilisant le Canal Première touche et le Canal Dernière touche hérités, vous pouvez obtenir des informations utiles sur les interactions de canal :

![](assets/mc-viz6.png)

Pour en savoir plus sur l’analyse marketing entre onglets, consultez cette vidéo : [Utilisation de l’analyse croisée pour explorer l’attribution marketing de base dans Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-cross-tab-analysis-to-explore-basic-marketing-attribution-in-analysis-workspace.html?lang=fr).
