---
title: Affichage des annotations
description: Affichage des annotations dans Analysis Workspace.
role: User, Admin
feature: Annotations
exl-id: 52b179fd-d9a4-4119-a3c6-f6a36f24f8ea
source-git-commit: ff38740116ac6f12033ebdc17cffa3250a30f3f7
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 84%

---

# Affichage des annotations

Les annotations se présentent de manière légèrement différente, selon leur emplacement et selon qu’elles s’étendent sur un seul jour ou sur une période.

## Affichage des annotations dans Workspace

| Type de <br/>visualisation | Description |
| --- | --- |
| **Graphique linéaire &#x200B;**<br/>**Un seul jour** | Lorsque vous sélectionnez ![Annoter](/help/assets/icons/Annotate.svg) dans un graphique linéaire, une fenêtre contextuelle contenant les détails de l’annotation s’affiche.<br/>![Annotation pour un seul jour](assets/annotation-single-day.png)<br/>Pour modifier l’annotation dans le [créateur d’annotations](create-annotations.md#annotation-builder), sélectionnez ![Modifier](/help/assets/icons/Edit.svg). Pour supprimer l’annotation, sélectionnez ![Supprimer](/help/assets/icons/Delete.svg). |
| **Graphique linéaire &#x200B;**<br/>**Période** | Lorsque vous sélectionnez ![Annoter une période](/help/assets/icons/AnnotateRange.svg), une fenêtre contextuelle contenant les détails de l’annotation s’affiche, ainsi qu’une ligne située en dessous qui indique la période.<br/>![Annotation de période](assets/annotation-range.png)Pour modifier l’annotation dans le [créateur d’annotations](create-annotations.md#annotation-builder), sélectionnez ![Modifier](/help/assets/icons/Edit.svg). Pour supprimer l’annotation, sélectionnez ![Supprimer](/help/assets/icons/Delete.svg). |
| **Tableau à structure libre** | Dans un tableau à structure libre, vous pouvez accéder à toutes les annotations à partir du bouton des annotations situé en haut à droite de la visualisation. Sélectionnez ![Annoter](/help/assets/icons/Annotate.svg) pour afficher toutes les annotations (sous forme de liste déroulante).<br/>![Tableau d’annotations](assets/annotations-table.png)<br/>Pour chaque annotation, vous pouvez sélectionner ![Modifier](/help/assets/icons/Edit.svg) pour modifier l’annotation dans le [créateur d’annotations](create-annotations.md#annotation-builder) et ![Supprimer](/help/assets/icons/Delete.svg) pour supprimer l’annotation. |

{style="table-layout:auto"}

## Affichage des annotations dans un fichier .pdf

Lorsque vous téléchargez ou envoyez votre projet sous forme de fichier .pdf, les annotations sont regroupées dans le fichier dans la section Résumé des annotations.

![Affichage en surbrillance d’un fichier PDF contenant des explications sur les annotations.](assets/annotations-pdf.png)


<!--
# View annotations

Annotations manifest slightly differently, depending on whether they span a single day or a date range.

## View annotations in Line charts or Tables

| Date | Appearance |
| --- | --- |
| **Single day** |   ![](assets/single-day.png)<p>When you hover over the annotation, you can see its details, you can edit it by selecting the pen icon, or you can delete it:<p> ![](assets/hover.png) |
| **Date range** |  The icon changes and when you hover over it, the date range appears.<p>![](assets/multi-day.png)<p>When you select it in the line chart, the annotation metadata appear, and you can edit or delete it:![](assets/multi-hover.png)<p>In a table, an icon appears on every date in the date range.<p>![](assets/multi-day-table.png)|
| **Overlapping annotations** | On days that have more than one annotation tied to them, the icon appears in a grey color.<p>![](assets/grey.png)<p>When you hover over the grey icon, all overlapping annotations appear:<p>![](assets/overlap.png) |

{style="table-layout:auto"}

## View annotations in a .pdf file

Since you cannot hover over icons in a .pdf file, this file (after export) provides notes of explanations at the bottom of a panel. Here is an example:

![](assets/ann-pdf.png)

## View annotations with non-trended data

Sometimes annotation are shown with non-trended data, but tied to a specific dimension. In that case, they appear only in a summary annotation in the bottom right corner. Here is an example:

![](assets/non-date.png)

The summary chart appears in all visualization types in the corner, not just in non-trended freeform tables and summary numbers. It also appears in visualizations like [!UICONTROL Donut], [!UICONTROL Flow],[!UICONTROL Fallout],[!UICONTROL Cohort], and so on.

![](assets/ann-summary.png)

-->