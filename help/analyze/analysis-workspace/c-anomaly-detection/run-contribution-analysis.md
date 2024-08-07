---
description: Exécution d’un rapport d’analyse des contributions dans un projet Workspace.
title: Exécution de l’analyse des contributions
role: User, Admin
exl-id: 20d1ba8d-3e4e-4702-ae28-5eb6bf00847b
feature: Anomaly Detection
source-git-commit: ee4772913c8b702658646755a2a11598c8530236
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 100%

---

# Exécution de l’analyse des contributions

[L’analyse des contributions](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) est un processus intensif de machine learning, conçu pour déterminer quels facteurs sont à l’origine d’une anomalie observée dans Adobe Analytics. Elle permet à l’utilisateur ou à l’utilisatrice de repérer, bien plus rapidement qu’il ne serait normalement possible, les opportunités ou les centres d’intérêt justifiant une analyse supplémentaire.

## Exécution de l’analyse des contributions {#run}

Dans un projet, vous pouvez invoquer l’analyse des contributions de deux façons :

* Dans un tableau à structure libre avec une granularité quotidienne, cliquez avec le bouton droit de la souris sur une ligne, puis sélectionnez **[!UICONTROL Exécuter l’analyse des contributions]**. Vous pouvez également l’exécuter sur les lignes qui ne présentent aucune anomalie.

  >[!NOTE]
  >
  >Actuellement, seule l’analyse des contributions avec une granularité quotidienne est prise en charge.

  ![](assets/run_ca.png)

* Dans un graphique en courbes, pointez avec la souris sur un point de données présentant une anomalie. Cliquez sur le lien **[!UICONTROL Analyser]** qui s’affiche.

  ![](assets/contribution-analysis.png)

1. (Facultatif) Après avoir cliqué sur **[!UICONTROL Exécuter l’analyse des contributions]** dans un tableau ou un graphique en courbes, vous pouvez réduire la portée de l’analyse (et donc l’accélérer) en [excluant des dimensions](#exclude).

1. Patientez pendant le chargement de l’analyse des contributions. Selon la taille de la suite de rapports et le nombre de dimensions, cette opération peut être longue. L’analyse des contributions traite les 50 000 premiers éléments par dimension.
1. Analysis Workspace charge ensuite un nouveau panneau Analyse des contributions directement dans ce projet.

   * Visualisation qui présente le nombre de **Visites** ce jour-là.
   * **Ligne de tendance des visites** mensuelle en fonction du contexte.
   * Les **principaux éléments** à l’origine de cette anomalie, triés par [note de contribution](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis), plus la mesure en question, ainsi qu’une mesure Visiteurs uniques qui replace la mesure dans son contexte du point de vue de la taille.

   * Le tableau [Segments générés](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=fr) (grappes des principaux éléments) identifie les associations des principaux éléments en fonction de la note de contribution, des occurrences de l’anomalie et du pourcentage global contribuant à la mesure anormale. Ces données sont ensuite regroupées dans un segment d’audience (Segment de contribution 1, Segment de contribution 2, etc.). Cliquez sur le bouton « i » (informations) pour afficher une définition de chaque segment automatique, y compris les principaux éléments qui le composent :

     ![](assets/auto_segment.png)

1. Puisque l’analyse des contributions fait maintenant partie d’Analysis Workspace, vous pouvez mettre à profit plusieurs de ses fonctions depuis un menu contextuel afin de rendre votre analyse plus significative, par exemple :

   * [Ventiler chaque élément de dimension par une autre dimension.](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)
   * [Déterminer la tendance d’une ou de plusieurs lignes.](/help/analyze/analysis-workspace/home.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [Ajouter de nouvelles visualisations.](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)
   * [Créer des alertes.](/help/components/c-alerts/intellligent-alerts.md)
   * [Créer ou comparer des segments.](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

>[!NOTE]
>
>L’anomalie en cours d’analyse est mise en évidence au moyen d’un point bleu dans l’analyse des contributions et les projets avec alertes intelligentes qui y sont liés. Ceci permet d’indiquer plus clairement l’anomalie en cours d’analyse.

## Exclusion de dimensions de l’analyse des contributions {#exclude}

Parfois, vous souhaiterez exclure certaines dimensions de l’analyse des contributions. Par exemple, vous pouvez ne pas attacher d’importance à des dimensions liées au navigateur ou au matériel et vous souhaitez accélérer l’analyse en les supprimant.

1. Une fois que vous avez cliqué sur **[!UICONTROL Exécuter l’analyse des contributions]** (ou **[!UICONTROL Analyser]** dans un graphique en courbes), le panneau **[!UICONTROL Dimensions exclues]** s’affiche.

1. Faites tout simplement glisser les dimensions non voulues dans le panneau **[!UICONTROL Dimensions exclues]**, puis enregistrez la liste en cliquant sur **[!UICONTROL Définir comme valeur par défaut]**. Ou bien, cliquez sur **[!UICONTROL Effacer tout]** pour recommencer la sélection des dimensions à exclure.

   ![](assets/exclude_dimensions.png)

1. Après avoir ajouté des dimensions à exclure (ou choisi de ne pas exclure), cliquez de nouveau sur **[!UICONTROL Exécuter l’analyse des contributions]**.
1. Si vous avez besoin de réviser la liste des dimensions exclues, double-cliquez simplement sur Dimensions, et la liste des dimensions exclues s’affiche :

   ![](assets/excluded-dimensions.png)

1. Supprimez simplement les dimensions non voulues en cliquant sur le x en regard, puis enregistrez la liste en cliquant sur **[!UICONTROL Définir comme valeur par défaut]**.
