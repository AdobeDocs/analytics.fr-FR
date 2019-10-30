---
description: valeur nulle
seo-description: valeur nulle
seo-title: Limites de l’espace de travail, limites connues dans Analysis Workspace
title: Limites connues dans Analysis Workspace
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Limites connues dans Analysis Workspace

Voici une liste des limites connues dans Analysis Workspace et ses composants connexes :

## Tableaux

* Les colonnes de comparaison de dates ne peuvent pas être ajoutées lorsque des plages de dates ou des mesures sont utilisées comme lignes d’un tableau.
* La mesure Créer d’après la sélection est désactivée lorsque des segments sont utilisés comme lignes d’un tableau. De plus, la mesure Créer d’après la sélection ne doit pas être appliquée aux colonnes alignées sur la date.
* La mise en forme conditionnelle des lignes de ventilation ne peut pas utiliser de plages personnalisées.
* Les lignes totales du tableau ne peuvent pas être de tendances lorsque vous calculez les totaux en additionnant le paramètre des valeurs de ligne (généralement utilisé avec les éléments de ligne statiques).
* [!UICONTROL L’analyse] des contributions peut être exécutée avec la granularité [!UICONTROL quotidienne] _uniquement_. Il ne peut pas être exécuté avec des données [!UICONTROL horaires], [!UICONTROL hebdomadaires], etc.,

## Visualisations

* Les visualisations qui tirent parti de la segmentation, telles que [!UICONTROL Abandon], [!UICONTROL Flux], [!UICONTROL cohorte]et [!UICONTROL Histogramme, ne peuvent pas accepter les mesures calculées comme entrées.]
* [!UICONTROL Flux]: Les dimensions d’entrée/de sortie, par exemple la page [!UICONTROL d’]entrée, ne peuvent pas être utilisées dans le flux.
* [!UICONTROL Cohorte]: Les non-entiers ne peuvent pas être utilisés comme critères de cohorte.

## Panneaux

* Comparaison des segments : Le segment [!UICONTROL Tous les autres] n’est pas créé si un modèle de segment est utilisé dans la zone de dépôt initiale.

## Composants &gt; Segments

* Certaines mesures et dimensions ne sont pas segmentables, telles que [!UICONTROL Occurrences], Visiteurs uniques, etc.
* Certains composants et opérateurs ne sont pas disponibles si un segment est créé à partir de Workspace (par opposition à être créé à partir de [!UICONTROL Composants &gt; Segments]). Par exemple, Adresse IP.

## Composants &gt; Mesures calculées

* Les mesures calculées ne peuvent pas être utilisées dans certaines visualisations. Voir Visualisations ci-dessus.
* Les mesures calculées ne peuvent pas être utilisées dans le panneau [!UICONTROL Attribution] , car les mesures calculées elles-mêmes peuvent inclure des modèles d’attribution distincts.
* Certains composants et opérateurs ne sont pas disponibles si une mesure calculée est créée à partir de Workspace (par opposition à être créée à partir de [!UICONTROL Composants &gt; Segments]). Par exemple, Adresse IP.

## Composants &gt; Plages de dates

* Les plages de dates personnalisées ne sont pas prises en charge [!UICONTROL Cette journée l’année]dernière, [!UICONTROL Ce jour le mois]dernier, etc.

## Composants &gt; Suites de rapports virtuelles

* Lorsque le traitement du temps de rapport est activé, certains composants ne sont pas pris en charge. Pour obtenir la liste complète, reportez-vous à la section [Traitement du temps de rapport](/help/components/vrs/vrs-report-time-processing.md).

## Composants &gt; Paramètres de rapport

* Certains paramètres de la page Paramètres [!UICONTROL du] rapport ne s’appliquent pas. Analysis Workspace utilise uniquement les paramètres [!UICONTROL Langue/Devise/Codage] situés en bas : Séparateur [!UICONTROL des milliers], Codage [!UICONTROL de rapports]planifiés et Caractère de séparation CSV.

## Attribution IQ

* Un sous-ensemble de mesures n’est pas pris en charge dans le QI [!UICONTROL de l’]attribution. Pour obtenir la liste complète, consultez la FAQ [sur l’](/help/analyze/analysis-workspace/attribution-iq/attribution-faq.md)attribution de QI.