---
description: 'Liste des limites connues d’Adobe Analysis Workspace et ses composants connexes :'
title: Limites connues dans Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: 520e970b-1387-4f70-985b-bfe397f4a21b
source-git-commit: f8a4b3442f7e9f631ba8e472c69fbc4d1cc3877e
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 90%

---

# Limites connues dans Analysis Workspace

Voici une liste des limites connues dans Analysis Workspace et ses composants connexes :

## Tableaux

* Impossibilité d’ajouter des colonnes de comparaison de dates lorsque des périodes ou des mesures sont utilisées comme lignes d’un tableau.
* L’option Créer une mesure d’après la sélection est désactivée lorsque des segments sont utilisés comme lignes d’un tableau. De plus, l’option Créer une mesure d’après la sélection ne doit pas être appliquée aux colonnes alignées sur la date.
* La mise en forme conditionnelle des lignes de ventilation ne peut pas utiliser de plages personnalisées.
* Les lignes totales du tableau ne peuvent pas être sous forme de tendances lorsque le paramètre Calculer les totaux en totalisant les valeurs est appliqué (généralement utilisé avec les éléments de ligne statique).
* [!UICONTROL L’analyse des contributions] peut être exécutée avec la granularité [!UICONTROL quotidienne] _uniquement_. Elle ne peut pas être exécutée par rapport à des données [!UICONTROL horaires], [!UICONTROL hebdomadaires], etc.

## Visualisations

* Les visualisations qui tirent parti de la segmentation, telles que [!UICONTROL Abandons], [!UICONTROL Flux], [!UICONTROL Cohorte] et [!UICONTROL Histogramme], ne peuvent pas accepter les mesures calculées en tant qu’entrées.
* [!UICONTROL Flux] : les dimensions d’entrée/de sortie, comme la [!UICONTROL page d’entrée], ne peuvent pas être utilisées dans Flux.
* [!UICONTROL Cohorte] : Les nombres non entiers ne peuvent pas être utilisés comme critères Cohorte.

## Panneaux

* Comparaison des segments : le segment [!UICONTROL Tous les autres] n’est pas créé si un modèle de segment est utilisé dans la zone de dépôt initiale.

## Composants > Segments

* Il n’est pas possible de segmenter certaines mesures et dimensions, comme [!UICONTROL Occurrences], [!UICONTROL Visiteurs uniques], etc.
* Segments ad hoc créés dans le [zone de dépôt du panneau](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=fr) sont un type de filtre rapide. Ils n’apparaissent pas dans le rail gauche de Workspace ou dans le gestionnaire de composants Segment, à moins qu’ils ne soient rendus publics. Pour plus d’informations, voir [Segments rapides](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

## Composants > Mesures calculées

* Il n’est pas possible d’utiliser les mesures calculées dans certaines visualisations. Voir « Visualisations » ci-dessus.
* Les mesures calculées ne peuvent pas être utilisées dans le panneau [!UICONTROL Attribution], car elles peuvent inclure elles-mêmes des modèles d’attribution distincts.
* Certains composants et opérateurs ne sont pas disponibles si une mesure calculée est créée à partir de Workspace (contrairement à une création à partir de [!UICONTROL Composants > Segments]). Par exemple, [!UICONTROL Adresse IP].

## Composants > Périodes

* Les périodes personnalisées ne prennent pas en charge [!UICONTROL Ce jour l’année dernière], [!UICONTROL Ce jour le mois dernier], etc.

## Composants > Suites de rapports virtuelles

* Lorsque la fonctionnalité de traitement de la période de rapport est activée, certains composants ne sont pas pris en charge. Pour obtenir la liste complète, reportez-vous à la section [Traitement de la période de rapport](/help/components/vrs/vrs-report-time-processing.md).

## Composants > Tous les composants > Paramètres des rapports

* Certains paramètres de la page [!UICONTROL Paramètres de rapport] ne s’appliquent pas. Analysis Workspace utilise uniquement les paramètres [!UICONTROL Langue/Devise/Encodage] situés en bas : [!UICONTROL Séparateur des milliers], [!UICONTROL Encodage d’un rapport planifié] et [!UICONTROL Caractère de séparation CSV].

## Attribution IQ

* Un sous-ensemble de mesures n’est pas pris en charge dans [!UICONTROL Attribution IQ]. Pour obtenir la liste complète, consultez la section [FAQ sur l’Attribution IQ](../attribution/faq.md).
