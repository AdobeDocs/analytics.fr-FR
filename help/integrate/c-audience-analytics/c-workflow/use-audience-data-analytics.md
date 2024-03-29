---
description: Vous pouvez utiliser les dimensions d’audience Adobe Audience Manager dans Analytics. Les segments intégrés sont de nouvelles dimensions Analytics appelées ID d’audience et Nom d’audience. Celles-ci peuvent être utilisées de la même façon que toutes les autres dimensions collectées par Analytics. Dans les flux de données, les ID d’audience sont stockés dans la colonne « mc_audiences ». Ces dimensions ne sont actuellement pas disponibles dans Data Workbench ou Livestream. Voici quelques exemples d’utilisation des dimensions d’audience
solution: Experience Cloud
title: Utilisation des données d’audience dans Analytics
feature: Audience Analytics
exl-id: c1c0a9de-4051-4073-82c1-5615b0f01fa9
source-git-commit: c947de8eaa4e4dc3a0c10989ef6ae450cebc1f3e
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 89%

---

# Utilisation des données d’audience dans Analytics

Vous pouvez utiliser les dimensions d’audience Adobe Audience Manager dans Analytics. Les segments intégrés sont de nouvelles dimensions Analytics appelées ID d’audience et Nom d’audience. Celles-ci peuvent être utilisées de la même façon que toutes les autres dimensions collectées par Analytics. Dans les flux de données, les ID d’audience sont stockés dans la colonne « mc_audiences ». Ces dimensions ne sont actuellement pas disponibles dans Data Workbench ou Livestream. Voici quelques exemples d’utilisation des dimensions d’audience :

## Analysis Workspace {#workspace}

Dans Analysis Workspace, les segments Adobe Audience Manager apparaissent sous la forme de deux dimensions.

1. Accédez à **[!UICONTROL Workspace]**.
1. Dans la liste des **[!UICONTROL Dimensions]**, sélectionnez les dimensions **[!UICONTROL ID d’audience]** ou **[!UICONTROL Nom d’audience]**. La dimension Nom d’audience est une classification conviviale de la dimension ID d’audience.

   ![](assets/aw-mcaudiences.png)

## Comparaison des segments  {#compare}

[Comparaison des segments](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html?lang=fr) détecte les différences les plus importantes sur le plan statistique entre deux segments. Les données d’audience peuvent être utilisées dans Comparaison des segments de deux façons : 1) sous la forme des 2 segments comparés et 2) sous la forme des éléments du tableau « Principaux éléments de dimension ».

1. Accédez à **[!UICONTROL Workspace]** et sélectionnez le panneau **[!UICONTROL Comparaison des segments]** dans le rail de gauche.

1. Recherchez [!UICONTROL Nom d’audience] dans le menu **[!UICONTROL Composant]**.

1. Ouvrez [!UICONTROL Nom d’audience] pour faire apparaître les éléments de dimension associés.
1. Faites glisser les audiences que vous souhaitez comparer dans le Générateur de comparaisons de segments.
1. (Facultatif) : Vous pouvez ajouter d’autres segments ou éléments de dimension ; il est possible de comparer jusqu’à 2 éléments.
1. Cliquez sur **[!UICONTROL Créer]**.

   Les dimensions ID et Nom d’audience apparaîtront automatiquement dans le tableau « Principaux éléments de dimension » car il s’agit de données de profil supplémentaires pour les deux segments comparés.

   ![](assets/aud-segcompare.png)

## Parcours client (flux) dans Analysis Workspace {#flow}

Les données de segment Adobe Audience Manager sont transmises à Analytics accès par accès et représentent l’appartenance à l’audience d’un visiteur à ce moment précis. Cela signifie qu’un visiteur peut appartenir à un segment (p. ex. « Sensibilisation »), puis répondre aux conditions d’un segment plus qualifié ultérieurement (p. ex. « Considération »). Vous pouvez utiliser [Flux](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html?lang=fr) dans Analysis Workspace pour visualiser le parcours d’un visiteur entre les audiences.

1. Accédez à **[!UICONTROL Workspace]** et sélectionnez la visualisation **[!UICONTROL Flux]** dans le rail de gauche.

1. Faites glisser la dimension [!UICONTROL Nom d’audience] dans le générateur de flux.
1. Cliquez sur **[!UICONTROL Créer]**.
1. (Facultatif) : Faites glisser les dimensions de votre choix dans la visualisation Flux pour créer un [Flux interdimensionnel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/flow/multi-dimensional-flow.html?lang=fr).

![](assets/flow-aamaudiences.png)

Les audiences peuvent également être utilisées dans les [Visualisations des abandons](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html?lang=fr).

## Visualisation de Venn dans Analysis Workspace  {#venn}

Les [visualisations de Venn](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/venn.html?lang=fr) affichent l’intersection entre 3 segments maximum.

1. Accédez à **[!UICONTROL Workspace]** et sélectionnez la visualisation de **[!UICONTROL Venn]** dans le rail de gauche.

1. Recherchez [!UICONTROL Nom d’audience] dans le menu Composants.
1. Ouvrez [!UICONTROL Nom d’audience] pour faire apparaître les éléments de dimension associés.
1. Faites glisser les audiences que vous souhaitez comparer dans le Générateur de diagrammes de Venn.
1. (Facultatif) : Vous pouvez ajouter d’autres segments ou éléments de dimension ; il est possible de comparer jusqu’à 3 éléments.
1. Cliquez sur **[!UICONTROL Créer]**.

![](assets/venn-viz.png)

## Créateur de segments {#builder}

Vous pouvez importer les dimensions d’audience dans le [Créateur de segments](/help/components/segmentation/segmentation-workflow/seg-build.md) Analytics, ainsi que les informations de comportement collectées par Analytics.

1. Accédez à **[!UICONTROL Composants]** > **[!UICONTROL Segments]**.
1. Cliquez sur **[!UICONTROL Ajouter]** pour définir un nouveau segment.
1. Après avoir nommé le segment, faites glisser la dimension [!UICONTROL Nom d’audience] vers le panneau Définitions.
1. (Facultatif) : Ajoutez d’autres critères au segment.
1. Enregistrez le segment.

   ![](assets/aud-segbuilder.png)

