---
title: Vue d’ensemble d’attribution
description: Découvrez le concept d’attribution du crédit d’un événement de succès à plusieurs éléments de dimension.
feature: Attribution
role: User, Admin
exl-id: 47a3523b-d9eb-4272-84b8-090b921cba13
TQID: 'https://experienceleague.adobe.com/JVkEgk1Becb6v4066bmg1JzkgFBKprFphrAx-xJroro'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 567
ht-degree: 87%

---

# Présentation d’Attribution

Attribution permet aux analystes de personnaliser la manière dont les éléments de dimension obtiennent du crédit pour les événements de succès. Par exemple :

1. Une personne qui visite votre site clique sur un lien de référencement payant vers l’une de vos pages produits. La personne ajoute le produit au panier, mais ne l’achète pas.
2. Le lendemain, elle voit une publication d’un ami ou d’une amie sur les médias sociaux, elle clique sur le lien, puis effectue l’achat.

Dans certains rapports, vous voudrez peut-être attribuer la commande au référencement payant. Dans d’autres rapports, vous voudrez peut-être attribuer la commande à Social. Attribution vous permet de contrôler cet aspect des rapports. Toutes les entreprises disposant d’Adobe Analytics Ultimate, Prime, Select ou Foundation peuvent en bénéficier. Si vous vous demandez quel type de contrat vous avez conclu avec Adobe, contactez l’équipe Adobe en charge des comptes de votre entreprise.

## Valeur d’attribution

Un parcours client donné n’est pas linéaire et est souvent imprévisible. Chaque client a son propre rythme. Il lui arrive souvent de revenir sur ses pas, de s’arrêter, de redémarrer ou d’adopter un autre comportement non linéaire. En raison de ces actions organiques, il est difficile de connaître l’impact des efforts marketing tout au long du parcours client. Cela complique également les efforts visant à relier plusieurs canaux de données.

<!--
![Attribution problem](assets/attribution_iq_problem.png)
-->

Adobe Analytics améliore l’attribution en vous permettant d’effectuer les tâches suivantes :

* Définir l’attribution à des médias autres que ceux achetés : tout élément (dimension, mesure, canal ou événement) peut être appliqué aux modèles (par exemple, recherche interne) et pas seulement aux campagnes marketing.
* Utilisez la comparaison illimitée de modèles d’attribution : comparez dynamiquement autant de modèles que vous le souhaitez.
* éviter les changements de mise en œuvre : avec le traitement de la période de rapport et les sessions contextuelles, le contexte du parcours client peut être intégré et appliqué lors de l’exécution ;
* construire la session qui correspond le mieux à votre scénario d’attribution ;
* Ventiler l’attribution par segments : comparez facilement les performances de vos canaux marketing sur n’importe quel segment important (par exemple, la nouvelle clientèle par rapport à la clientèle régulière, le produit X par rapport au produit Y, le niveau de fidélité ou la valeur vie client (CLV)).
* inspecter le croisement des canaux et l’analyse multi-touch : utilisation des histogrammes et diagrammes de Venn ainsi que des résultats de l’attribution des tendances ;
* analyser visuellement des séquences marketing importantes : explorez les chemins d’accès qui ont mené à la conversion sur le plan visuel par le biais de visualisations à plusieurs nœuds de flux et d’abandons ;
* créer des mesures calculées : utilisez n’importe quel nombre de méthodes d’attribution.

## Fonctionnalités

Attribution propose les fonctionnalités suivantes :

* [Panneau Attribution](../c-panels/attribution.md) : comparez rapidement les dimensions et les mesures avec différents modèles d’attribution.
* [Appliquer l’attribution à une mesure](../visualizations/freeform-table/column-row-settings/column-settings.md) : utilisez une attribution autre que celle par défaut sur une mesure d’un projet.
* [Appliquer l’attribution à une répartition](../components/dimensions/t-breakdown-fa.md) : utilisez une attribution autre que celle par défaut sur une répartition.
* [Comparer des modèles d’attribution](../components/apply-create-metrics.md) : comparez rapidement les différents modèles d’attribution pour n’importe quelle mesure.

## Vidéos


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Attribution dans les tableaux à structure libre](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-attribution-iq-in-freeform-tables){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Attribution dans les mesures calculées](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/attribution-iq-in-calculated-metrics){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Utilisation du panneau Attribution](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-the-attribution-iq-panel){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Ajout de comparaisons côte à côte de modèles d’attribution](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/adding-side-by-side-comparisons-of-attribution-iq-models){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Outils Adobe Analytics ne prenant pas en charge l’attribution

Les outils qui ne prennent pas en charge l’API Analytics 2.0, comme [Report Builder hérité](/help/analyze/legacy-report-builder/home.md), ne prennent pas en charge l’attribution.
