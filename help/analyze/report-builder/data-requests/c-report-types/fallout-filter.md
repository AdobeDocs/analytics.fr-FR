---
description: Décrit les étapes d’application de filtres à un rapport Abandon.
title: Filtrage d’un rapport sur les abandons à l’aide de l’Assistant Requête
topic: Report builder
uuid: 269e900e-23bd-48d8-9bac-69e3167a9c18
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filtrage d’un rapport sur les abandons à l’aide de l’Assistant Requête

Décrit les étapes d’application de filtres à un rapport Abandon.

Cet exemple affiche le rapport Page - Abandon.

1. In Adobe Report Builder, click **[!UICONTROL Create]** to open the Request Wizard.
1. Sélectionnez la suite de rapports appropriée.
1. In the tree view on the left, select **[!UICONTROL Paths]** &gt; **[!UICONTROL Page]** &gt; **[!UICONTROL Page Fallout]**.

   ![](assets/page_fallout.png)

1. Configurez les plages de [dates](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)appropriées.
1. Cliquez sur **[!UICONTROL Suivant]**.
1. In Step 2 of the Wizard, under **[!UICONTROL Row Labels]**, click the **[!UICONTROL Define Checkpoints]** link. (Dans un rapport d’abandon, vous devez toujours définir des éléments de chemin, à la différence d’un rapport de cheminement où un modèle est pré-appliqué.)

   ![](assets/define_checkpoints.png)

1. Select the **[!UICONTROL Filter]** option.

1. In the **[!UICONTROL Define Site Section Fallout Checkpoints]** dialog, define checkpoints from a range of cells or from a list. Puis, cliquez sur **[!UICONTROL OK]**.
1. Choisissez d’effectuer la sélection depuis une plage de cellules ou depuis une liste.
1. If you select from a list, click **[!UICONTROL Add]** to select checkpoints to add to the fallout path. Vous pouvez définir entre 3 et 8 points de contrôle. (Search for available elements by clicking **[!UICONTROL More]**.)

   For more information on refining the filter, see [Filter Dimensions](/help/analyze/report-builder/layout/c-filter-dimensions/filter-dimensions.md). 1. Move **[!UICONTROL Available Elements]** from the left column to the right by selecting them and clicking the orange arrow.
1. Click **[!UICONTROL OK]** three times, then click **[!UICONTROL Finish]**.

   Le rapport devrait à présent s’actualiser.
