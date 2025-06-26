---
description: Les mesures calculées et les mesures calculées avancées sont des mesures personnalisées que vous pouvez créer à partir de mesures existantes.
keywords: Mesures calculées ; mesures calculées avancées
title: Mesures calculées et mesures calculées avancées
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: d85e6990998e3c153ef969d8dc7f3a4835f683bf
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 36%

---

# Vue d’ensemble des mesures calculées

Mesures calculées et personnalisées que vous pouvez créer à partir de mesures existantes.

Les mesures calculées offrent un moyen très flexible de créer, de gérer et d’organiser des mesures. Les mesures calculées vous permettent, en tant que responsables du marketing, chefs de produit et analystes, de poser des questions sur les données sans avoir à modifier votre implémentation [!DNL Analytics].

Les mesures calculées sont disponibles dans chaque package de [!DNL Analytics], mais le pack Adobe Analytics Foundation pour Experience Cloud se limite aux mesures calculées de base, y compris les types de format [ (décimal, temps, pourcentage, devise)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md), [ les modifications d’affectation (par défaut, linéaire, participation, etc.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md), [types de mesures (standard, total)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) et [opérateurs de base](c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md#operators) (ajout, soustraction, multiplication et division).


Pour plus d’informations](https://helpx.adobe.com/fr/legal/product-descriptions/adobe-analytics.html) voir la [Description du produit Adobe Analytics .

<!--
Here is a comparison of calculated metrics and advanced calculated metrics capabilities: 

| [Format types (decimal, time, percent, currency)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Attribution changes (default, linear, participation, etc.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Metric types (standard, total)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
|  Basic operators (add, subtract, multiply, divide)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Apply segments](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md)  | ![StopCircle](/help/assets/icons/StopCircle.svg)  | Yes  |
| [Basic functions (count, abs value, mean, etc)](/help/components/c-calcmetrics/cm-reference/cm-functions.md)  | No  | Yes  |
| [Advanced functions (regression, if/then, t-score, etc)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md)  | No  | Yes  |

-->

## Fonctionnalités  {#section_A0A5C275B68A4D628950BBB0B1EE631F}

Vous pouvez

* [Création de mesures](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-workflow.md) dans [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Détection des anomalies] et [!UICONTROL Analyse des contributions].
* [Créer des mesures segmentées](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) dérivées au moment de l’exécution du rapport, sans avoir à modifier l’implémentation. Par exemple, vous pouvez créer une mesure pour *Nouveaux visiteurs*, avec un décompte des personnes pour lesquelles il s’agit de la première session.

* [Partage de mesures](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md) entre les suites de rapports. Cela signifie que toutes les mesures nouvellement créées s’appliquent à toutes les suites de rapports de la même société de connexion.

* [Incorporez des fonctions statistiques](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) pour vous aider à mieux décrire vos données. Par exemple, vous pouvez comptabiliser le nombre d’éléments d’un rapport ou ajouter le nombre d’écarts types pour chaque élément.

## Limites

Certaines fonctionnalités [!DNL Analytics] ne permettent pas d’utiliser des mesures calculées :

* [!UICONTROL Abandons] dans [!UICONTROL Analysis Workspace]
* [!UICONTROL Analyse de cohortes] dans Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segments]
* [!DNL Analytics] for [!DNL Target]


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Mesures calculées](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Mesures calculées segmentées dans les segments](https://video.tv.adobe.com/v/25409?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

<!--

Here is a short overview of the [!UICONTROL Calculated metrics] tools: 

|Tool|Capabilities|
|--- |--- |
| [Calculated metric builder](c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)| The capabilities are: <ul><li>Create calculated and advanced calculated metrics using advancmd allocation models.</li><li>Add segments inline to metric formulas</li><li>Compare segments in the same report. For example, compare local visitors vs. international visitors.</li><li>Use statistical functions</li><li>Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it)</li><li>Copy definitions into new metrics</li><li>Provide an inline metric preview</li><li>Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up</li><li>Tag metrics</li></ul>|
|Calculated Metric Manager|<ul><li>Share metrics with others</li<li>Approve and curate metrics</li><li>Organize (tag) your metrics so people can find them</li><li>Delete metrics</li><li>Rename metrics</li></ul>|
|Metric Selector rail|Lets you search for and add/apply metrics to the report. You can also change the  sort order (options are: alphabetical, recommended, frequently used, recently used.) In addition, you can filter on Report Suites to show only metrics created in a specific report suite.  To access this Metric Selector, click the Metrics icon  to the left of a report. |
|API for Calculated Metrics|Part of the Adobe Analytics 2.0 API set.|

-->

>[!MORELIKETHIS]
>
>[Créer des mesures](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-workflow.md)
>>[Créer des mesures](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)
>>[Utilisez des fonctions ](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-using-functions.md)
>
