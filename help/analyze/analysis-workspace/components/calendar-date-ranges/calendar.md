---
description: Utilisez le calendrier et les périodes pour spécifier des périodes dans Analysis Workspace.
title: Présentation des périodes
feature: Date Ranges
role: User, Admin
exl-id: fbf4bc18-65ba-4e39-96c1-4c41a8e3baa9
source-git-commit: ff38740116ac6f12033ebdc17cffa3250a30f3f7
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 96%

---


# Vue d’ensemble des périodes

Dans un projet Workspace, vous utilisez généralement le [calendrier dans un panneau](/help/analyze/analysis-workspace/c-panels/panels.md#calendar) pour spécifier la période des visualisations dans ce panneau.

Les composants de période vous permettent de définir et de remplacer les paramètres de calendrier du panneau.


## Utilisation de périodes

Vous pouvez utiliser un composant de période pour redéfinir le calendrier du panneau.

Vous pouvez également utiliser une période dans un tableau à structure libre en tant que mesure ou dimension.

![Utilisation de période](assets/date-ranges-usage.png)

- **Mesure**. Par exemple, pour comparer une dimension pour deux mois différents pour une mesure spécifique.
- **Dimension**. Pour comparer une mesure sur différents éléments de dimension pour la dimension de période.

>[!NOTE]
>
>Lorsque vous utilisez des périodes dans un tableau à structure libre, elles remplacent le calendrier spécifié pour le panneau auquel appartient le tableau à structure libre.
>

Vous utilisez une période comme vous [utiliseriez n’importe quel composant](/help/analyze/analysis-workspace/components/analysis-workspace-components.md#analysis-workspace-components). Vous faites glisser la période à partir du panneau du composant ![Calendrier](/help/assets/icons/Calendar.svg) **[!UICONTROL Périodes]** et déposez le composant sur :

- **[!UICONTROL Calendrier]** : vous ![Basculer](/help/assets/icons/Switch.svg) **[!UICONTROL Remplacez]** la configuration actuelle du calendrier par la période.
- **En-tête de colonne de mesure** : vous ![Basculer](/help/assets/icons/Switch.svg) **[!UICONTROL Remplacez]** la mesure, ![Ajouter](/help/assets/icons/Add.svg)**[!UICONTROL Ajoutez &#x200B;]**&#x200B;la période en tant que mesure ou ![Filtrer](/help/assets/icons/Filter.svg)**[!UICONTROL &#x200B; Filtrez &#x200B;]**&#x200B;la mesure à l’aide du composant de période.
- **En-tête de colonne Dimension** : vous ![Basculer](/help/assets/icons/Switch.svg) **[!UICONTROL Remplacez]** les dimensions actuelles. La nouvelle dimension s’intitule désormais **[!UICONTROL Périodes]**. Une fois que la dimension est Périodes, vous pouvez ![Ajouter](/help/assets/icons/Add.svg)**[!UICONTROL Ajouter &#x200B;]**&#x200B;des périodes supplémentaires en tant qu’éléments de dimension.
- **Élément de dimension** : vous effectuez une ![Répartition](/help/assets/icons/Breakdown.svg) **[!UICONTROL Répartition]** de l’élément de dimension spécifique par période.

Vous pouvez également ajouter une colonne de période directement dans une visualisation de tableau à structure libre :

1. Dans une colonne de mesure, sélectionnez dans le menu contextuel :

   - **[!UICONTROL Ajoutez une colonne de période]**. Vous pouvez choisir entre les options suggérées basées sur le calendrier actuel ou créer une [période personnalisée](#custom-date-ranges).
   - **[!UICONTROL Comparez des périodes]**. Vous pouvez choisir entre une option suggérée basée sur le calendrier actuel ou créer une [période personnalisée](#custom-date-ranges).

1. Selon votre sélection, d’autres colonnes de périodes sont ajoutées au tableau à structure libre.

## Périodes par défaut

Analysis Workspace propose un certain nombre de périodes par défaut.


| Jour | Semaine | Mois | Trimestre | Année |
|---|---|---|---|---|
| Today | Cette semaine | Ce mois-ci | Ce trimestre | Cette année |
| Hier | Cette semaine (sauf aujourd’hui) | Ce mois (sauf aujourd’hui) | Ce trimestre (sauf aujourd’hui) | Cette année (sauf aujourd’hui) |
| 2 jours auparavant | 2 semaines auparavant | 2 mois auparavant |   |  |
| 3 jours auparavant | 3 semaines auparavant | 3 mois auparavant |  | |
| 7 derniers jours | Semaine dernière | Mois dernier | Dernier trimestre | Année dernière |
| 14 derniers jours | 2 dernières semaines complètes | 2 derniers mois complets | 4 derniers trimestres complets | |
| 30 derniers jours | 3 dernières semaines complètes | 3 derniers mois complets | | |
| 60 derniers jours | 4 dernières semaines complètes | 6 derniers mois complets | | |
| 90 derniers jours | 12 dernières semaines complètes | 12 derniers mois complets | | |
| 7 derniers jours complets | 52 dernières semaines complètes | 13 derniers mois complets | | |
| 14 derniers jours complets | | | | |
| 30 derniers jours complets | | | | |
| 90 derniers jours complets | | | | |

<table style="table-layout:fixed">

## Périodes personnalisées

Vous pouvez créer vos propres périodes personnalisées. Consultez [Créer une période](create.md) pour connaître les différentes options disponibles pour créer des périodes. Vous pouvez ensuite créer, modifier et enregistrer des périodes dans le [créateur de périodes](create.md#date-range-builder).

Utilisez le [gestionnaire de périodes](manage.md) pour gérer les périodes.



<!--
# Calendar and date ranges overview {#date-range}

>[!CONTEXTUALHELP]
>id="components_dateranges_endtime"
>title="End time"
>abstract="End times always include 59 seconds."



In the calendar, you can specify dates and date ranges, or select a preset.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Calendar and date ranges overview](https://video.tv.adobe.com/v/328075?quality=12&learn=on&captions=fre_fr){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


Calendar selections apply at the panel level, but you have the option to apply them to all panels. When you click a date range in Workspace, the interface displays the current calendar month and the previous calendar month. You can adjust these two calendars by clicking the right and left arrows in each respective upper corner.

![Calendar](assets/aw_calendar2.png){width="60%"} 

## Select and apply date ranges {#select-apply}

The first click on a calendar starts a date range selection. The second click completes a date range selection, which becomes highlighted. If the `Shift` key is held down (or right-click is used), it appends to the currently selected range.

You can also drag dates (and time dimensions) into a Workspace project. You can select specific days, weeks, months, years, or a rolling date.

[Using Date Ranges and Calendar in Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html?lang=fr) (4:07)

| Setting | Description |
|--- |--- |
|Selected Days|Selected days/weeks/months/years.|
|Make date range components relative to panel calendar| If disabled, any date range components used within a table, visualization, or panel drop zone override the panel calendar. <p>If enabled, any date range components used within a table, visualization, or panel drop zone are in relation to the panel date range. For example, if the panel date range is set to November 1 through November 30, and a Last Week date range component is used in a freeform table, the information in the freeform table refers to the last week in October. |
|Use rolling dates| Rolling dates allow you to generate a dynamic report that looks forward or backward for a set period of time based on when you ran the report. For example, if you want to report on all Orders placed "Last Month" (based on the Created Date field) and ran that report in December, you'd see orders placed in November. If you ran that same report in January, you'd see orders placed in December.<ul><li>**[!UICONTROL Date Preview]**: Indicates what time period the rolling calendar encompasses.</li><li>**[!UICONTROL Start]**: You can choose among current day, current week, current month, current quarter, current year.</li><li>**[!UICONTROL End]**: You can choose among current day, current week, current month, current quarter, current year.</li></ul>To view an example, see [Custom date ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md). <br>Selected by default.|
|Date Range|Lets you pick a preset date range. Last 30 days is the default. **[!UICONTROL This week/month/quarter/year (excluding today)]** lets you choose from date ranges that do not include partial-day data from today.|
|Apply to All Panels|Lets you not only change the selected date range for the current panel, but also for all other panels within the project.|
|Apply|Applies the date range to this panel only.|

## About relative panel date ranges {#relative-panel-dates}

If you're working in Workspace, you can make the date range components relative to the panel calendar. 
Three common use cases where you'll see relative panel dates take effect are Combo charts, Key metrics summary, and Freeform table date ranges.

To use relative panel date ranges

1. Select the **Workspace** tab.
1. Select **Blank project**.
1. Add dimensions, metrics, and segments from the left rail. 
1. Click the panel date range field to toggle the relative panel date range setting.
1. Select **Make date range components relative to panel calendar**.
    * Select the option to make the date range components relative to the panel calendar.
        If relative dates are selected, then rolling dates will be based on the start date of the panel calendar and not today's date.
    * If this option isn't selected, then rolling dates will be based on today's date.

    ![relative panel dates](assets/relative-date-selected.png){width="60%"} 

1. Click **Apply**.
    The relative dates are shown in the upper-right.

    ![relative dates in freeform ](assets/relative-date-range1.png)

## Guidelines for relative panel date ranges {#guidelines}

Keep in mind the following guidelines when using relative panel date ranges.

### Formulas and relative date ranges {#formula-relative-dates}

If you have relative dates selected, all date formulas will use the panel's start date as the starting point.

### Custom calendars and relative date ranges {#custom-calendar-formulas}

When you use a week-based custom calendar and you add months or years, the formula calculates the offset of the day in the given period. The actual date may be different because of the offset. The formula chooses the day landing in the same place in the custom calendar. For example, the third Friday of the third week in a custom calendar.

### About segments that use rolling dates and relative panel date ranges {#segments-relative-dates}

If you build a segment or use a segment with a rolling date, for example, the Last 7 Days or the Last 2 Weeks, and you click on the segment preview, it will start the rolling date from *Today* instead of the panel start date. As a result the preview for the segment will not match when you actually use the segment in the table. The preview is impacted, not the segment itself. 

## Guidelines for panel date ranges and previews {#guidelines-panel-dates}

* Starting with the February release, component and data previews will be based on the panel date range and not the last 90 days. 
* All components listed in the left rail will be available based on the panel date range. 
* All date previews in the segment and calculated metric builders will be based on the panel date range (unless accessed from the component managers, which do not have an associated panel, they will still be based on the last 90 days). 
* Any data previews will display data or components based on the panel date range.

-->