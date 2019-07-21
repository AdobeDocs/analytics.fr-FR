---
description: valeur nulle
seo-description: valeur nulle
seo-title: Limitations de Workspace, limites connues dans Analysis Workspace
title: Limites connues dans Analysis Workspace
translation-type: tm+mt
source-git-commit: 9d6b35c7c6de6fcb49fea3b662ff8bc9044b5e29

---


# Limites connues dans Analysis Workspace

Voici la liste des limites connues dans Analysis Workspace et les composants associés :

## Tableaux

* Les colonnes de comparaison de dates ne peuvent pas être ajoutées lorsque des plages de dates ou des mesures sont utilisées comme lignes d'un tableau.
* La création d'une mesure d'après la sélection est désactivée lorsque les segments sont utilisés comme lignes d'un tableau. De plus, la mesure Créer d'après la sélection ne doit pas être appliquée aux colonnes alignées par date.
* La mise en forme conditionnelle des lignes de ventilation ne peut pas utiliser de plages personnalisées.
* Le nombre total de lignes ne peut pas être tendance lorsque Calculer les totaux en additionnant le paramètre des valeurs de ligne est appliqué (généralement utilisé avec les éléments de ligne statiques).
* [!UICONTROL L'analyse des contributions] peut être exécutée à la [!UICONTROL granularité quotidienne] _uniquement_. It cannot be run against [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## Visualisations

* Visualizations that leverage segmentation, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL Flux]: Les dimensions d'entrée/sortie, par exemple Page d'entrée, ne peuvent pas être utilisées dans Flux.
* [!UICONTROL Cohorte]: Les non-entiers ne peuvent pas être utilisés comme critères de cohorte.

## Panneaux

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## Composants &gt; Segments

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Certain components and operators are unavailable if a segment is created from Workspace (as opposed to being created from [!UICONTROL Components &gt; Segments]). Par exemple, adresse IP.

## Composants &gt; Mesures calculées

* Les mesures calculées ne peuvent pas être utilisées dans certaines visualisations. Voir Visualisations ci-dessus.
* Calculated metrics cannot be used in the [!UICONTROL Attribution] panel, since calculated metrics themselves can include separate attribution models.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components &gt; Segments]). For example, [!UICONTROL IP Address].

## Composants &gt; Plages de dates

* Custom date ranges do not support [!UICONTROL This day last year], [!UICONTROL This day last month], etc.

## Composants &gt; Suites de rapports virtuelles

* Lorsque le traitement du temps de rapport est activé, certains composants ne sont pas pris en charge. For a full list, see [Report Time Processing](/help/components/vrs/vrs-report-time-processing.md).

## Composants &gt; Paramètres de rapport

* Some of the settings on the [!UICONTROL Report Settings] page do not apply. Analysis Workspace uses only the [!UICONTROL Language/Currency/Encoding] settings at the bottom: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding], and [!UICONTROL CSV Separator Character].

## Attribution IQ

* A subset of metrics is not supported in [!UICONTROL Attribution IQ]. For a full list, see the [Attribution IQ FAQ](/help/analyze/analysis-workspace/attribution-iq/attribution-faq.md).