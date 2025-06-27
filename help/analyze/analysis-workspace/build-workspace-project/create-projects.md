---
description: Découvrez comment créer un projet dans Analysis Workspace.
title: Création de projets
feature: Workspace Basics
role: User, Admin
exl-id: 24193013-1361-43fc-b129-c44f207d9101
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 91%

---

# Créer des projets {#create-projects}


Les [projets](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) dans Analysis Workspace vous permettent de créer et de visualiser des analyses critiques.  Ces analyses peuvent être partagées avec des parties prenantes au sein de votre organisation ou en dehors.

1. Dans Adobe Analytics, sélectionnez **[!UICONTROL Workspace]**.

1. Sélectionnez **[!UICONTROL Projets]** dans le panneau de gauche, puis **[!UICONTROL Créer un projet]**.

1. Sélectionnez **Projet Workspace vierge** pour créer votre projet Workspace à l’aide d’un navigateur.

   Consultez [Carte de performance mobile vierge](/help/analyze/mobile-app/curator.md) pour plus d’informations sur la création d’un projet de carte de performance mobile que vous pouvez partager avec d’autres parties prenantes à l’aide d’une application mobile.

1. Sélectionnez [!UICONTROL **Créer**].


Maintenant que vous avez créé un projet Workspace vierge, assurez-vous de connaître l’interface utilisateur d’[Analysis Workspace](/help/analyze/analysis-workspace/home.md). Une fois l’interface connue, vous pouvez créer votre projet. Pour ce faire, procédez comme suit :

![Exemple de projet](assets/example-project.png)

* Ajoutez des [panneaux](/help/analyze/analysis-workspace/c-panels/panels.md) à votre projet. Par exemple, **[!DNL Example Panel]** ➊.

* Ajoutez des [visualisations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) à vos panneaux. Par exemple :
   * **[!DNL Line]** [Visualisation](/help/analyze/analysis-workspace/visualizations/line.md) sous forme de lignes➋
   * **[!DNL US States]** [Visualisation sous forme de ](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)tableau à structure libre➌
* Ajoutez des [composants](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) à vos visualisations. Par exemple :
   * **[!DNL US States]** [dimension](/help/components/dimensions/overview.md) ➍
   * **[!DNL Unique Visitors]** [mesure](/help/analyze/analysis-workspace/components/apply-create-metrics.md) ➎
   * **[!DNL Average Revenue Per Order]** [mesure calculée](/help/components/c-calcmetrics/cm-overview.md) ➏
   * **[!DNL Visits from Mobile Devices]** [segment](/help/components/segmentation/seg-overview.md) ➐
   * **[!DNL Last Month]** [période](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) ➑
   * **[!DNL Example]** [annotation](/help/analyze/analysis-workspace/components/annotations/overview.md) ➒


## Informations et paramètres du projet {#project-info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="Comptage des instances répétées"
>abstract="Ce paramètre indique si les instances répétées sont comptabilisées dans les rapports.<br/><br/>Remarque : ce paramètre ne s’applique pas aux visualisations de flux ou d’abandons."

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="Comptage des instances répétées"
>abstract="Ce paramètre indique si les instances répétées sont comptabilisées dans les rapports.<br/>Remarque : ce paramètre ne s’applique pas aux visualisations de flux ou d’abandons."


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="Autoriser les commentaires"
>abstract="Lorsque cette option est activée, une zone de commentaires est disponible dans le rail de droite du projet dans Analysis Workspace."


Les paramètres du projet fournissent des informations sur le projet actif au niveau du projet.

![Fenêtre Informations et paramètres du projet.](./assets/projectinfo.png)

Les paramètres incluent :

| Paramètre | Description |
|---|---|
| Nom du projet | Nom donné au projet. Double-cliquez dessus pour le modifier. |
| Personne propriétaire | Nom de la personne propriétaire du projet. |
| Dernière modification | Date de la dernière modification du projet. |
| Balises | Répertorie les balises appliquées à un projet afin de faciliter la catégorisation. |
| Description | Une description est utile pour clarifier l’objet d’un projet. Double-cliquez dessus pour la modifier. |
| Comptage des instances répétées | Spécifie si les instances répétées sont comptabilisées dans les rapports. Remarque : ce paramètre ne s’applique pas aux visualisations de flux ou d’abandons. |
| Affichage des annotations | Spécifie si les annotations s’affichent pour ce projet ou non. |
| [Palette de couleurs du projet](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md) | Vous pouvez modifier la palette de couleurs catégoriques utilisée dans Workspace en choisissant parmi les palettes prêtes à l’emploi qui ont été optimisées pour le daltonisme ou en spécifiant votre palette personnalisée. Cette fonction affecte de nombreux éléments dans Workspace, y compris la plupart des visualisations. |
| [Densité d’affichage](/help/analyze/analysis-workspace/build-workspace-project/view-density.md) | Vous permet de voir plus de données sur l’écran en réduisant l’espacement vertical du panneau de gauche, des tableaux à structure libre et des tableaux de cohortes. |



<!--
# Create projects in Analysis Workspace

[Projects](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) in Analysis Workspace allow you to view business-critical analyses that can be shared with stakeholders inside or outside your organization. 

For general information about how to get started using Analysis Workspace, see [Analysis Workspace overview](/help/analyze/analysis-workspace/home.md).

The following sections describe how to create a project and start adding the key building blocks for any Analysis Workspace project: panels, visualizations, and components.

## Create a project from a blank project or a report

1. In Adobe Analytics, select [!UICONTROL **Workspace**].

1. Choose whether to create a blank project or to create a project from a report:

   +++Create a blank project

   1. On the [!UICONTROL **Workspace**] tab, select the [!UICONTROL **Projects**] tab on the left side of the page, then select [!UICONTROL **Create project**].

   1. Choose whether to create a blank project or a blank mobile scorecard

      * **Blank project** if you plan to share your analysis from the browser 
      * [**Blank mobile scorecard**](/help/analyze/mobile-app/curator.md) if you plan to share your analysis from the Adobe Analytics dashboards mobile app.

   1. Select [!UICONTROL **Create**].

   +++

   +++Create a project from a report
   
      1. On the [!UICONTROL **Workspace**] tab, select the [!UICONTROL **Reports**] tab on the left side of the page.

      1. Search for or navigate to the report you want to use, then select it when it appears.

          A set of standard reports is available by default. In addition, your organization might have created custom reports for you to choose from.
          
      1. Select [!UICONTROL **Project**] > [!UICONTROL **Save**] to save the report as a new project.

          For more information about reports, see "Navigate the Reports tab" in [Adobe Analytics landing page](/help/analyze/landing.md).

   +++

1. Next, you need to add panels, visualizations, and components to your project. First, add panels to your project in Analysis Workspace, as described in [Add panels to the project](#add-panels-to-the-project). You can then add visualizations to any panels. Finally, you can add components to any panels or visualizations.

## Add panels to the project {#panels}

[Panels](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html) are the foundation to any project in Analysis Workspace. Panels are used to organize the content (visualizations and components) of a project. 

Many of the panels provided in Analysis Workspace generate a full set of analyses based on a few user inputs. 

To add a panel:

1. Select the [!UICONTROL **Panels**] icon in the left rail.

   ![](assets/build-panels.png)

1. Search for the panel you want to add. When it appears in the left rail, drag it into your project.

1. Add visualizations to your panel, as described in [Add visualizations to the project](#add-visualizations-to-the-project). 

   Alternatively, you can add components directly to a panel, as described in [Add components to the project](#add-components-to-the-project).

## Add visualizations to the project

[Visualizations](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) (such as a freeform table, a bar chart, or a line chart) can be used to visually bring data to life. 

>[!TIP]
>
>Freeform tables are the most common type of visualization, and are the foundation for interactive data analysis. For more details about how to work with Freeform tables in Analysis Workspace, see [Freeform table](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md).

To add a visualization:

1. Select the **[!UICONTROL Visualizations]** icon in the left rail.

   ![](assets/build-visualizations.png)

1. Search for the visualization you want to add. When it appears in the left rail, drag it to a panel within your project. 

1. Add components to the visualization, as described in [Add components to the project](#add-components-to-the-project).

## Add components to the project

[Components](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) make up the actual data of any project. You can add components to visualizations or to panels.

>[!TIP]
>
>For information about each component, select the Info icon next to a component's name in the left rail, or see the [Analytics Components Guide](/help/components/home.md).

Following is basic information about how to add a component to a project in Analysis Workspace. For more detailed information about adding the various types of components (dimensions, metrics, segments, and date ranges), see [Use components in Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).

To add a component to a project in Analysis Workspace:

1. Select the **[!UICONTROL Components]** icon in the left rail.

   ![](assets/build-components.png)

1. Scroll to or search for the component you want to add, then drag it to a panel or visualization within your project. 

   For example, you can drag a segment to the segment drop zone in a panel header.

   ![drop a segment in the drop zone](assets/segment-dropzone.png)

   For more information about adding components to projects, see [Use components in Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).

1. (Optional) Share the project as described in [Save and share the project](#save-and-share-the-project).

## Save and share the project

As you create an analysis in Analysis Workspace, your work is [automatically saved](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md). 

When you finish building out the project and it's gathering actionable insights, the project is ready to be consumed by others. You can share the project with users and groups in your organization, or even with people outside your organization. For information about sharing a project, see [Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md).
-->