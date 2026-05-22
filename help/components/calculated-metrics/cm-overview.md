---
description: Découvrez les mesures calculées que vous pouvez créer à partir de mesures existantes.
keywords: Mesures calculées
title: Vue d’ensemble des mesures calculées
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
autotag-review: '2026-05-22T11:11:01.439Z'
TQID: 'https://experienceleague.adobe.com/JjrOp20i9YXIvlNjvUIyPoyoqOaAlYzIi2r25IXogHQ'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 317
ht-degree: 75%

---

# Vue d’ensemble des mesures calculées

Les mesures calculées sont des mesures personnalisées que vous pouvez créer à partir de mesures existantes.

Les mesures calculées sont des mesures personnalisées que vous pouvez créer à partir de mesures existantes. Les mesures calculées offrent un moyen flexible de créer, gérer et traiter des mesures personnalisées qui vous permettent d’analyser vos données sans avoir à modifier votre implémentation.

Les mesures calculées sont disponibles dans chaque package de [!DNL Analytics], mais le pack Adobe Analytics Foundation pour CX Enterprise se limite aux mesures calculées de base, y compris les types de format [ (décimal, temps, pourcentage, devise)](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md), les modifications d’affectation [ (par défaut, linéaire, participation, etc.)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md), les types de mesures [ (standard, total)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md) et les [opérateurs de base](workflow/c-build-metrics/cm-build-metrics.md#operators) (ajouter, soustraire, multiplier et diviser).


Pour plus d’informations, consultez la section [Description du produit Adobe Analytics](https://helpx.adobe.com/fr/legal/product-descriptions/adobe-analytics.html).

<!--
Here is a comparison of calculated metrics and advanced calculated metrics capabilities: 

| [Format types (decimal, time, percent, currency)](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Attribution changes (default, linear, participation, etc.)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Metric types (standard, total)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
|  Basic operators (add, subtract, multiply, divide)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Apply segments](/help/components/calculated-metrics/workflow/c-build-metrics/metrics-with-segments.md)  | ![StopCircle](/help/assets/icons/StopCircle.svg)  | Yes  |
| [Basic functions (count, abs value, mean, etc)](/help/components/calculated-metrics/cm-reference/cm-functions.md)  | No  | Yes  |
| [Advanced functions (regression, if/then, t-score, etc)](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)  | No  | Yes  |

-->

## Fonctionnalités {#section_A0A5C275B68A4D628950BBB0B1EE631F}

Vous pouvez

* [Créez des mesures](/help/components/calculated-metrics/workflow/cm-workflow.md) dans [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Détection des anomalies] et [!UICONTROL Analyse des contributions].
* [Créez des mesures segmentées](/help/components/calculated-metrics/workflow/c-build-metrics/metrics-with-segments.md) qui sont dérivées au moment de l’exécution du rapport, sans avoir à modifier l’implémentation. Par exemple, vous pouvez créer une mesure *Nouveaux visiteurs et visiteuses*, avec un décompte des personnes pour lesquelles il s’agit de la première session.

* [Partagez des mesures](/help/components/calculated-metrics/workflow/cm-sharing.md) dans l’ensemble des suites de rapports. Cela signifie que toutes les mesures nouvellement créées s’appliquent à toutes les suites de rapports de la même société de connexion.

* [Incluez des fonctions statistiques](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md) pour vous aider à mieux décrire vos données. Par exemple, vous pouvez comptabiliser le nombre d’éléments d’un rapport ou ajouter le nombre d’écarts types pour chaque élément.

## Limites

Certaines fonctionnalités [!DNL Analytics] ne permettent pas d’utiliser des mesures calculées :

* [!UICONTROL Abandons] dans [!UICONTROL Analysis Workspace]
* [!UICONTROL Analyse de cohortes] dans Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segments]
* [!DNL Analytics] for [!DNL Target]


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Mesures calculées](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Mesures calculées segmentées dans les segments](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-segmented-metrics){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

<!--

Here is a short overview of the [!UICONTROL Calculated metrics] tools: 

|Tool|Capabilities|
|--- |--- |
| [Calculated metric builder](workflow/c-build-metrics/cm-build-metrics.md)| The capabilities are: <ul><li>Create calculated and advanced calculated metrics using advancmd allocation models.</li><li>Add segments inline to metric formulas</li><li>Compare segments in the same report. For example, compare local visitors vs. international visitors.</li><li>Use statistical functions</li><li>Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it)</li><li>Copy definitions into new metrics</li><li>Provide an inline metric preview</li><li>Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up</li><li>Tag metrics</li></ul>|
|Calculated Metric Manager|<ul><li>Share metrics with others</li<li>Approve and curate metrics</li><li>Organize (tag) your metrics so people can find them</li><li>Delete metrics</li><li>Rename metrics</li></ul>|
|Metric Selector rail|Lets you search for and add/apply metrics to the report. You can also change the  sort order (options are: alphabetical, recommended, frequently used, recently used.) In addition, you can filter on Report Suites to show only metrics created in a specific report suite.  To access this Metric Selector, click the Metrics icon  to the left of a report. |
|API for Calculated Metrics|Part of the Adobe Analytics 2.0 API set.|

-->

>[!MORELIKETHIS]
>
>[Créer des mesures](/help/components/calculated-metrics/workflow/cm-workflow.md)
>[Création de mesures](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)
>[Utiliser des fonctions](/help/components/calculated-metrics/workflow/c-build-metrics/cm-using-functions.md)
>
