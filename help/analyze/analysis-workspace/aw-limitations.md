---
description: 'Liste des limites connues d’Adobe Analysis Workspace et ses composants connexes :'
title: Limites connues dans Analysis Workspace
translation-type: tm+mt
source-git-commit: 06d2e64fc72c911828f089de5c487117251e060e

---


# Limites connues dans Analysis Workspace

Voici une liste des limites connues dans Analysis Workspace et ses composants connexes :

## Tableaux

* Impossibilité d’ajouter des colonnes de comparaison de dates lorsque des périodes ou des mesures sont utilisées comme lignes d’un tableau.
* L’option Créer une mesure d’après la sélection est désactivée lorsque des segments sont utilisés comme lignes d’un tableau. De plus, l’option Créer une mesure d’après la sélection ne doit pas être appliquée aux colonnes alignées sur la date.
* La mise en forme conditionnelle des lignes de ventilation ne peut pas utiliser de plages personnalisées.
* Les lignes totales du tableau ne peuvent pas être sous forme de tendances lorsque le paramètre Calculer les totaux en totalisant les valeurs est appliqué (généralement utilisé avec les éléments de ligne statique).
* [!UICONTROL Contribution Analysis] peut être exécuté avec la [!UICONTROL daily] granularité _uniquement_. It cannot be run against [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## Visualisations

* Visualizations that leverage segmentation, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL Flow]: Dimensions d’entrée/de sortie, p. ex. [!UICONTROL Entry page], ne peut pas être utilisé dans Flux.
* [!UICONTROL Cohort]: Les non-entiers ne peuvent pas être utilisés comme critères de cohorte.

## Panneaux

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## Composants > Segments

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Certain components and operators are unavailable if a segment is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). Par exemple, Adresse IP.

## Composants > Mesures calculées

* Il n’est pas possible d’utiliser les mesures calculées dans certaines visualisations. Voir « Visualisations » ci-dessus.
* Les mesures calculées ne peuvent pas être utilisées dans le panneau [!UICONTROL Attribution], car elles peuvent inclure elles-mêmes des modèles d’attribution distincts.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). Par exemple : [!UICONTROL IP Address].

## Composants > Périodes

* Les plages de dates personnalisées ne sont pas prises en charge [!UICONTROL This day last year], [!UICONTROL This day last month], etc.

## Composants > Suites de rapports virtuelles

* Lorsque la fonctionnalité de traitement de la période de rapport est activée, certains composants ne sont pas pris en charge. Pour obtenir la liste complète, reportez-vous à la section [Traitement de la période de rapport](/help/components/vrs/vrs-report-time-processing.md).

## Composants > Paramètres de rapport

* Some of the settings on the [!UICONTROL Report Settings] page do not apply. Analysis Workspace utilise uniquement les [!UICONTROL Language/Currency/Encoding] paramètres situés en bas : [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding]et [!UICONTROL CSV Separator Character].

## Attribution IQ

* A subset of metrics is not supported in [!UICONTROL Attribution IQ]. Pour obtenir la liste complète, consultez la section [FAQ sur l’Attribution IQ](c-panels/attribution/attribution-faq.md).
