---
description: Découvrez comment utiliser le gestionnaire de segments pour gérer les segments tels que partager, filtrer, baliser, approuver, copier, supprimer des segments et les marquer comme favoris.
title: Gestion des segments
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 16%

---

# Gérer les segments


Vous pouvez [partager](t-seg-share.md), [segment](t-seg-filter.md), [balise](seg-tag.md), [approuver](seg-approve.md), renommer, [copier](seg-copy.md), supprimer, exporter des segments et marquer les segments comme [favori](t-seg-favorite.md) depuis une interface de gestion [!UICONTROL Segment] centrale. Pour gérer les segments :

* Sélectionnez **[!UICONTROL Composants]** dans l’interface principale, puis sélectionnez **[!UICONTROL Segments]**.


>[!NOTE]
>
>Les segments rapides que vous créez dans un projet Workspace spécifique n’apparaissent pas dans le gestionnaire [!UICONTROL Segment], sauf si vous avez mis le segment à disposition de tous vos projets.
>

## Gestionnaire de segments

Le gestionnaire de segments comporte les éléments d’interface suivants :

![&#x200B; Interface des segments &#x200B;](assets/segments-manager.png)

### Liste des segments

La liste des segments affiche ➊ tous les segments que vous possédez, les segments qui ont été étendus à tous vos projets et les segments qui ont été partagés avec vous. La liste comporte les colonnes suivantes :

| Colonne | Description |
| --- | --- |
| ![Contour en forme d’étoile](/help/assets/icons/StarOutline.svg) | Sélectionnez pour favoriser ![Étoile](/help/assets/icons/Star.svg) ou annuler la préférence ![ÉtoileContour](/help/assets/icons/StarOutline.svg) un segment. Voir [Marquer le segment comme favori](t-seg-favorite.md) |
| **[!UICONTROL Titre et description]** | Pour modifier le segment, sélectionnez le lien de titre, qui ouvre le [créateur de segments](seg-build.md). Un segment partagé est indiqué par la mention ![Partager](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Suites de rapports]** | Suite de rapports à laquelle ce segment s’applique. |
| **[!UICONTROL Propriétaire]** | Propriétaire du segment. En tant qu’utilisateur, vous ne voyez que les segments que vous possédez ou les annotations qui sont partagées avec vous. |
| **[!UICONTROL Balises]** | Balises pour ce segment. |
| **[!UICONTROL Partagé avec]** | Nombre d’individus ou de groupes avec lesquels vous avez partagé le segment. Sélectionnez cette option pour ouvrir la boîte de dialogue **[!UICONTROL Partager le composant]**. Voir [Partager des segments](t-seg-share.md) pour plus d’informations. |
| **[!UICONTROL Publié]** | Indique si le [segment est publié](seg-publish.md) dans Experience Cloud. |
| **[!UICONTROL Date de modification]** | Date et heure de la dernière modification du segment. |

Utilisez ![Paramètres de colonne](/help/assets/icons/ColumnSetting.svg) pour spécifier les colonnes à afficher.

### Barre d’actions

Vous pouvez agir sur les segments à l’aide de la barre d’actions ➋. La barre d’actions contient les actions suivantes :

| Action | Description |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Ajouter]** | Ajoutez un autre segment à l’aide du [créateur de segments](seg-build.md). |
| ![Recherche](/help/assets/icons/Search.svg) [!UICONTROL *Recherche par titre*] | Lorsqu’aucun segment n’est sélectionné dans la liste, recherchez des segments à l’aide de ce champ de recherche. |
| ![Label](/help/assets/icons/Label.svg) **[!UICONTROL Étiquette]** | Balisez les segments sélectionnés. Dans la boîte de dialogue **[!UICONTROL Baliser le segment]**, sélectionnez ou désélectionnez les balises des segments sélectionnés. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les balises des segments sélectionnés. Voir [Balisage de segments](seg-tag.md) pour plus d’informations. |
| ![Partager](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Partager]** | Partagez les segments sélectionnés. Dans la boîte de dialogue **[!UICONTROL Partager le segment]**, vous pouvez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des individus ou des groupes* ou sélectionner **[!UICONTROL Organisation]** ou **[!UICONTROL Groupes]**. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les détails de partage pour les segments sélectionnés. Voir [Partager des segments](t-seg-share.md) pour plus d’informations. |
| ![Supprimer](/help/assets/icons/Delete.svg) **[!UICONTROL Supprimer]** | Supprimez les segments sélectionnés. Il vous est demandé de confirmer. |
| ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Renommer]** | Renommez un seul segment sélectionné. Lorsque cette option est sélectionnée, vous pouvez renommer le segment en ligne. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approuver]** | Valider les segments sélectionnés. Voir [Approuver les segments](seg-approve.md) pour plus d’informations. |
| ![Copier](/help/assets/icons/Copy.svg) **[!UICONTROL Copier]** | Copiez le segment sélectionné. Les nouveaux segments sont créés avec les mêmes nom et suffixe `(Copy)`. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exporter au format CSV]** | Exportez les segments vers un fichier `Segments List.csv`. |

### Barre de filtres actifs

La barre de filtrage affiche ➌ les segments actifs appliqués à partir du panneau de filtrage à la liste des segments (le cas échéant). Vous pouvez supprimer rapidement un filtre à l’aide de ![CrossSize75](/help/assets/icons/CrossSize75.svg). Si plusieurs filtres sont spécifiés, vous pouvez supprimer tous les filtres à l’aide de l’option **[!UICONTROL Tout supprimer]**.

### Panneau Filtrer

Vous pouvez filtrer la liste des segments à l’aide du ![&#x200B; du panneau de gauche &#x200B;](/help/assets/icons/Filter.svg)Filtrer **&#x200B;**&#x200B;Filtrer➍. Le panneau de filtrage affiche le type de filtre et le nombre de segments qui respectent le filtre spécifique. Sélectionnez ![Filtrer](/help/assets/icons/Filter.svg) pour activer/désactiver l’affichage du panneau Filtre.

Voir [Filtrer la liste des segments](t-seg-filter.md) pour plus d’informations.


<!--

The Segment manager offers many ways of curating segments, such as sharing, filtering, tagging, approving, copying, deleting, and marking as favorites.

The Analytics Segment manager shows you all the segments you own and that have been shared with you. Admin-level users can see all segments in the organization. This overview presents the user interface and the capabilities of the Segment manager. 

![Segments manager](assets/segments-manager.png)

## Access the Segment manager

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Segments]**.

   Or 

   In an existing report, select the Segments icon ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) in the left navigation, then select **[!UICONTROL Manage]**.

## Available actions in the Segment manager

In the Segment manager, you can:

* [Filter segments](/help/components/segmentation/segmentation-workflow/t-seg-filter.md)

* [Mark segments as favorites](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)

* [Approve segments](/help/components/segmentation/segmentation-workflow/seg-approve.md)

* [Tag segments](/help/components/segmentation/segmentation-workflow/seg-tag.md)

* [Share segments](/help/components/segmentation/segmentation-workflow/t-seg-share.md)

* Export a segment to a CSV file.

* [Copy segments](/help/components/segmentation/segmentation-workflow/seg-copy.md)

* [Delete segments](/help/components/segmentation/segmentation-workflow/seg-delete.md)

## Configure columns

You can configure the information displayed for each segment in the Segment manager by configuring the columns that are displayed.

To configure the visible columns in the Segment manager:

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Segments]**. 

1. In the Segment manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Segment manager.

   The following columns are available:

   | Column title | Description  |
   |---|---|
   | Title and description | These values are provided in the Segment builder. To edit the title and description, select the title link to open the Segment builder.  |
   | Favorites  | Displays star icons next to each segment, allowing you to mark segments as favorites. For more information, see [Mark segments as favorites](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md). |
   | Report suites  | This column indicates in which report suite the segment was last saved.  |
   | Owner  | Indicates who owns the segment. As a non-Admin, you can see only segments you own or those that were shared with you.  |
   | Tags (not checked in column selector, hence column not appearing)  | Tags that were applied to the segment, either by you or by people who shared the segment with you.  |
   | Shared with  | Lists individuals or groups (Admin only) or All (Admin only) that you shared the segment with. <p>When a segment is being shared by you or with you, a share icon displays next to the segment name.</p>|
   | Date modified  | Shows the date that the segment was last modified.  |
   | Used in | Shows where segments are currently being used, and how many times they are being used in each area. <p>For example, if the segment is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**].</p> <p>Select the value in this column to see the breakdown of where the segments are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Alerts (2)**]). Furthermore, you can view the list of items where the segments are being used. For example, so see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of segments being used in that area:</p>  <ul><li>[!UICONTROL **Projects**]<p>Contains segments that were [created in the segment builder](/help/components/segmentation/segmentation-workflow/seg-build.md) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains segments that were [created as quick segments](/help/analyze/analysis-workspace/components/segments/quick-segments.md) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Alerts**]</li><li>[!UICONTROL **Calculated metrics**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a segment includes another segment in its definition, any use of that segment is not shown in the [!UICONTROL **Used in**] column. If a segment is included in the definition of another type of component (such as a calculated metric), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p>  |
   | Last used | Shows the date when the segment was last used in any of the following component types: <ul><li>Alerts</li><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li><li>Segments</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |
   
   {style="table-layout:auto"}

## How-To Video {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

This [Adobe Analytics video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html) gives a short overview of how to use the Segment manager.

-->