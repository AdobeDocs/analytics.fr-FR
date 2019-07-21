---
description: Décrit les étapes d’application de filtres à un rapport Abandon.
seo-description: Décrit les étapes d’application de filtres à un rapport Abandon.
seo-title: Filtrage d'un rapport d'abandons à l'aide de l'Assistant Requête
solution: Analytics
title: Filtrage d'un rapport d'abandons à l'aide de l'Assistant Requête
topic: Créateur de rapports
uuid: 269 e 900 e -23 bd -48 d 8-9 bac -69 e 3167 a 9 c 18
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Filtrage d'un rapport d'abandons à l'aide de l'Assistant Requête

Décrit les étapes d’application de filtres à un rapport Abandon.

Cet exemple affiche le rapport Page - Abandon.

1. In Adobe Report Builder, click **[!UICONTROL Create]** to open the Request Wizard.
1. Sélectionnez la suite de rapports appropriée.
1. In the tree view on the left, select **[!UICONTROL Paths]** &gt; **[!UICONTROL Page]** &gt; **[!UICONTROL Page Fallout]**.

   ![](assets/page_fallout.png)

1. Configure the appropriate [date ranges](../../../../analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md).
1. Click **[!UICONTROL Next]**.
1. In Step 2 of the Wizard, under **[!UICONTROL Row Labels]**, click the **[!UICONTROL Define Checkpoints]** link. (Dans un rapport d’abandon, vous devez toujours définir des éléments de chemin, à la différence d’un rapport de cheminement où un modèle est pré-appliqué.)

   ![](assets/define_checkpoints.png)

1. Select the **[!UICONTROL Filter]** option.

1. In the **[!UICONTROL Define Site Section Fallout Checkpoints]** dialog, define checkpoints from a range of cells or from a list. Puis, cliquez sur **[!UICONTROL OK]**.
1. Choisissez d’effectuer la sélection depuis une plage de cellules ou depuis une liste.
1. If you select from a list, click **[!UICONTROL Add]** to select checkpoints to add to the fallout path. Vous pouvez définir entre 3 et 8 points de contrôle. (Search for available elements by clicking **[!UICONTROL More]**.)

   For more information on refining the filter, see [Filter Dimensions](../../../../analyze/report-builder/layout/c-filter-dimensions/filter-dimensions.md#concept_9C0518E2CF604AADA97DDBB1B4ECAAF8). 1. Move **[!UICONTROL Available Elements]** from the left column to the right by selecting them and clicking the orange arrow.
1. Click **[!UICONTROL OK]** three times, then click **[!UICONTROL Finish]**.

   Le rapport devrait à présent s’actualiser.