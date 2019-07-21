---
description: valeur nulle
seo-description: valeur nulle
seo-title: Exécution de l’analyse des contributions
title: Exécution de l’analyse des contributions
uuid: 5282 a 5 f 9-0771-4974-93 cb -335204 bde 114
translation-type: tm+mt
source-git-commit: 8b2feced9fd503395d06dc12c8e5d7985ca89161

---


# Exécution de l’analyse des contributions

L’analyse des contributions est un processus intensif d’apprentissage automatique, conçu pour déterminer quels facteurs sont à l’origine d’une anomalie observée dans Adobe Analytics. Elle permet à l’utilisateur de repérer, bien plus rapidement qu’il ne serait normalement possible, les opportunités ou les centres d’intérêt justifiant une analyse supplémentaire.

## Exécution de l’analyse des contributions {#section_7D2C5E48A5664727941DF4C90976D9DC}

Dans un projet, vous pouvez invoquer l’analyse des contributions de deux façons :

* In a freeform table with daily granularity, right-click any row and select **[!UICONTROL Run Contribution Analysis]**. Vous pouvez également l’exécuter sur les lignes qui ne présentent aucune anomalie.

   >[!NOTE]
   >
   >Actuellement, nous ne prenons en charge l'analyse des contributions qu'avec une granularité quotidienne.

   ![](assets/run_ca.png)

* Dans un graphique en courbes, pointez avec la souris sur un point de données présentant une anomalie. Cliquez sur le lien **[!UICONTROL Analyser]qui s’affiche.**

   ![](assets/contribution-analysis.png)

1. (Facultatif) Après avoir cliqué sur **[!UICONTROL Exécuter l’analyse des contributions]** dans un tableau ou un graphique en courbes, vous pouvez réduire la portée de l’analyse (et donc l’accélérer) en [excluant des dimensions](../../../../analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md#section_F6932F4BF74544B5872164E7B1E0C6FC).

1. Patientez pendant le chargement de l’analyse des contributions. Selon la taille de la suite de rapports et le nombre de dimensions, cette opération peut être longue. L’analyse des contributions traite les 50 000 premiers éléments par dimension.
1. Analysis Workspace charge ensuite un nouveau panneau Analyse des contributions directement dans ce projet. Si vous avez déjà utilisé l’analyse des contributions dans Reports &amp; Analytics, de nombreux panneaux vous seront familiers :

   * Visualisation qui présente le nombre de **Visites** ce jour-là.
   * **Ligne de tendance des visites** mensuelle en fonction du contexte.
   * Les **principaux éléments** à l’origine de cette anomalie, triés par [note de contribution](https://marketing.adobe.com/resources/help/en_US/analytics/contribution/ca_contribution_score.html), plus la mesure en question, ainsi qu’une mesure Visiteurs uniques qui replace la mesure dans son contexte du point de vue de la taille.

   * Le tableau [Segments générés](https://marketing.adobe.com/resources/help/en_US/analytics/contribution/ca_workflow_premium.html) (grappes des principaux éléments) identifie les associations des principaux éléments en fonction de la note de contribution, des occurrences de l’anomalie et du pourcentage global contribuant à la mesure anormale. Ces données sont ensuite regroupées dans un segment d’audience (Segment de contribution 1, Segment de contribution 2, etc.). Cliquez sur le bouton « i » (informations) pour afficher une définition de chaque segment automatique, y compris les principaux éléments qui le composent :

      ![](assets/auto_segment.png)

1. Puisque l’analyse des contributions fait maintenant partie d’Analysis Workspace, vous pouvez mettre à profit plusieurs de ses fonctions depuis un menu contextuel afin de rendre votre analyse plus significative, par exemple :

   * [Ventiler chaque élément de dimension par une autre dimension.](../../../../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md#task_B594DA2476E84DFDA8279E831F0BD9C4)
   * [Déterminer la tendance d’une ou de plusieurs lignes](../../../../analyze/analysis-workspace/analysis-workspace-features.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [Ajouter de nouvelles visualisations.](../../../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#concept_09242627629147A88A68F1506954C276)
   * [Créer des alertes.](/help/components/c-alerts/intellligent-alerts.md)
   * [Créer ou comparer des segments.](../../../../analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md#concept_74FAC1C6D0204F9190A110B0D9005793)

>[!NOTE]
>
>Nous mettons en évidence l'anomalie analysée avec un point bleu dans l'analyse des contributions et les projets d'alerte intelligente qui y sont liés. Ceci permet d’indiquer plus clairement l’anomalie en cours d’analyse.

## Exclude dimensions from Contribution Analysis {#section_F6932F4BF74544B5872164E7B1E0C6FC}

Parfois, vous souhaiterez exclure certaines dimensions de l’analyse des contributions. Par exemple, vous pouvez ne pas attacher d’importance à des dimensions liées au navigateur ou au matériel et vous souhaitez accélérer l’analyse en les supprimant.

1. Une fois que vous avez cliqué sur **[!UICONTROL Exécuter l’analyse des contributions]** (ou **[!UICONTROL Analyser]dans un graphique en courbes), le panneau** Dimensions exclues] s’affiche.**[!UICONTROL **

1. Faites tout simplement glisser les dimensions non voulues dans le panneau **[!UICONTROL Dimensions exclues]**, puis enregistrez la liste en cliquant sur **[!UICONTROL Définir comme valeur par défaut]**. Ou bien, cliquez sur **[!UICONTROL Effacer tout]pour recommencer la sélection des dimensions à exclure.**

   ![](assets/exclude_dimensions.png)

1. Après avoir ajouté des dimensions à exclure (ou choisi de ne pas exclure), cliquez de nouveau sur **[!UICONTROL Exécuter l’analyse des contributions].**
1. Si vous avez besoin de réviser la liste des dimensions exclues, double-cliquez simplement sur Dimensions, et la liste des dimensions exclues s’affiche :

   ![](assets/excluded-dimensions.png)

1. Supprimez simplement les dimensions non voulues en cliquant sur le x en regard, puis enregistrez la liste en cliquant sur **[!UICONTROL Définir comme valeur par défaut]**.

