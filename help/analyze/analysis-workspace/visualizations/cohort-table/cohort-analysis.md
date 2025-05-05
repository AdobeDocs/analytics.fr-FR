---
title: Quʼest-ce que lʼanalyse des cohortes et comment fonctionne-t-elle ?
description: Analysez plus précisément les données sur votre audience et triez-les en groupes apparentés grâce à lʼanalyse des cohortes. En savoir plus sur l’analyse des cohortes dans Analysis Workspace.
feature: Cohort Analysis
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: 1ce002a513860ce15dc8a70825d26795fd93eb1d
workflow-type: ht
source-wordcount: '708'
ht-degree: 100%

---

# Vue d’ensemble de la table de cohorte {#cohort-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="Table de cohorte"
>abstract="Créez une visualisation de cohorte pour regrouper les utilisateurs et utilisatrices en fonction de la fin d’un événement et analyser l’évolution de l’engagement et de l’attrition client."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="Table de cohorte"
>abstract="Regroupez les utilisateurs et utilisatrices en fonction de la fin d’un événement, puis analysez l’évolution de l’engagement et de l’attrition client.<br/><br/>**Paramètres **<br/>**Critères d’inclusion** : composants utilisés pour définir vos cohortes initiales de visiteurs et visiteuses.<br/>**Critères de retour** : composants utilisés pour savoir si un visiteur ou une visiteuse revient."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Cet article présente la table de cohorte dans_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Voir [Table de cohorte](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/visualizations/cohort-table/cohort-analysis) pour la_ version ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** de cet article._

>[!ENDSHADEBOX]



Une *cohorte* est un groupe de personnes partageant des caractéristiques communes au cours d’une période spécifique. La visualisation ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Table de cohorte]** s’avère utile, par exemple, pour savoir de quelle façon une cohorte interagit avec une marque. Vous pouvez facilement déceler des changements de tendances, pour y réagir en conséquence. (Vous trouverez des explications sur l’[!UICONTROL analyse des cohortes] sur le Web, tel le cours [Cohort Analysis 101](https://fr.wikipedia.org/wiki/Cohort_analysis) (en anglais).)

Après avoir créé un rapport de cohorte, vous pouvez en traiter les composants (dimensions, mesures et filtres spécifiques), puis partager le rapport avec les personnes de votre choix. Consultez la section [Traitement et partage](/help/analyze/analysis-workspace/curate-share/curate.md).

Exemples d’utilisation de la [!UICONTROL Table de cohorte] :

* Lancez des campagnes conçues pour déclencher une action spécifique.
* Ajustez le budget marketing exactement au bon moment au cours du cycle de vie des clients.
* Déterminer quand terminer un essai ou une offre pour en optimiser la valeur.
* Trouver des idées de test A/B dans des domaines tels que le prix, le cheminement de mise à niveau, etc.

La [!UICONTROL Table de cohorte] est disponible pour tous les clientes et clients Customer Journey Analytics avec des droits d’accès à [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analyse de cohorte dans Analysis Workspace](https://video.tv.adobe.com/v/3430072/?quality=12&learn=on&captions=fre_fr){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>Lʼ[!UICONTROL Analyse de cohorte] ne prend pas en charge les mesures qui ne peuvent pas être filtrées (y compris les mesures calculées), les mesures non entières (telles que les recettes) ou les occurrences. Seules les mesures pouvant être utilisées dans les filtres peuvent être utilisées dans une [!UICONTROL Analyse de cohorte]. En outre, elles ne peuvent être incrémentées que d’un à la fois.

Les tables de cohorte de Customer Journey Analytics prennent en charge les mesures à base double (ou toute mesure numérique). Par exemple, la valeur Purchase.Value (valeur double) peut être utilisée comme mesure d’inclusion/retour. En outre, toutes les mesures transmises à Adobe Experience Platform par le biais du connecteur source Analytics sont également doublées.

## Fonctionnalités de la table de cohorte

Les sections suivantes décrivent les fonctionnalités d’analyse de cohorte qui permettent un contrôle précis des cohortes que vous créez.

Pour plus d’informations sur la création d’une cohorte et l’exécution d’un rapport [!UICONTROL Analyse de cohorte], voir [Configurer une table de cohorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### Table de [!UICONTROL rétention]

Table de cohorte de [!UICONTROL Rétention] sur les visiteurs et visiteuses récurrents : chaque cellule indique le nombre brut et le pourcentage de visiteurs et visiteuses dans la cohorte qui ont effectué l’action durant cette période. Vous pouvez inclure jusqu’à 3 mesures et 10 filtres.

![Rapport de cohorte de rétention indiquant les unités et le pourcentage de personnes dans la cohorte.](assets/retention-report.png)

### Table [!UICONTROL Attrition]

Une table de cohorte [!UICONTROL Attrition] est l’inverse d’un tableau de rétention. Elle indique les personnes qui ont abandonné ou n’ont jamais rempli les critères de retour de votre cohorte au fil du temps. Vous pouvez inclure jusqu’à 3 mesures et 10 filtres.

![Table Attrition montrant les unités et le pourcentage de personnes qui ne répondaient pas aux critères de retour pour une cohorte.](assets/churn-report.png)

### [!UICONTROL Calcul variable]

Vous pouvez calculer la rétention ou l’attrition en fonction de la colonne précédente, et non de la colonne incluse, ce qu’on appelle calcul variable.

![Rapport de cohorte sur la rétention présentant des calculs basés sur une colonne de données précédente.](assets/retention-report-rolling.png)

### Tableau [!UICONTROL Latence]

Un tableau de latence mesure la durée écoulée avant et après un événement d’inclusion. Mesurer la latence est un excellent outil avant et après analyse. La colonne **[!UICONTROL Inclus]** se trouve au centre de la table, tandis que les périodes avant et après l’événement d’inclusion sont affichées des deux côtés.

![Rapport de cohorte indiquant le temps écoulé avant et après un événement.](assets/retention-report-latency.png)

### Cohorte [!UICONTROL Dimension personnalisée]

Vous pouvez créer des cohortes en fonction d’une dimension sélectionnée, et non des cohortes en fonction du temps, qui sont les cohortes par défaut. Utilisez des dimensions telles que [!UICONTROL Ville géographique], [!UICONTROL Canal marketing], [!UICONTROL campagne], [!UICONTROL produit], [!UICONTROL page], [!UICONTROL région] ou toute autre dimension pour afficher l’évolution de la rétention. En fonction des différentes valeurs de ces dimensions.

![Rapport de cohorte présentant un rapport personnalisé avec des dimensions sélectionnées et non la cohorte temporelle par défaut.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[Configurez une table de cohorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).
>



<!--
A *`cohort`* is a group of people sharing common characteristics over a specified period. [!UICONTROL Cohort Analysis] is useful, for example, when you want to learn how a cohort engages with a brand. You can easily spot changes in trends, then respond accordingly. (Explanations of [!UICONTROL Cohort Analysis] are available on the web, such as at [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

After creating a cohort report, you can curate its components (specific dimensions, metrics, and segments), then share the cohort report with anyone. See [Curate and Share](/help/analyze/analysis-workspace/curate-share/curate.md).

Examples of what you can do with [!UICONTROL Cohort Analysis]:

* Launch campaigns designed to spur a desired action.
* Shift marketing budget at exactly the right time in the customer lifecycle.
* Recognize when to end a trial or an offer, in order to maximize value.
* Gain ideas for A/B testing in areas such as pricing, upgrade path, and so on.

[!UICONTROL Cohort Analysis] is available for all Adobe Analytics customers with access rights to [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Cohort analysis in Analysis Workspace](https://video.tv.adobe.com/v/3430089?quality=12&learn=on&captions=fre_fr){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis] does not support non-segmentable metrics (including calculated metrics), non-integer metrics (such as Revenue), or Occurrences. 
>
>Only metrics that can be used in segments can be used in [!UICONTROL Cohort Analysis], and they can only be incremented by >1 at a time. 

## Cohort Analysis capabilities

The following sections describe Cohort Analysis features that allow for fine-tuned control over the cohorts you are building.

For more detailed information about creating a cohort and running a [!UICONTROL Cohort Analysis] report, see [Configure a Cohort Analysis report](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### [!UICONTROL Retention] Table

A [!UICONTROL Retention] cohort report returns visitors: each data cell shows the raw number and percentage of visitors in the cohort who did the action during that time period. You can include up to 3 metrics and up to 10 segments.

![](assets/retention-report.png)


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Calculate rolling retention](https://video.tv.adobe.com/v/3430166?quality=12&learn=on&captions=fre_fr){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



### [!UICONTROL Churn] Table

A [!UICONTROL Churn] cohort is the inverse of a retention table and shows the visitors who fell out or never met the return criteria for your cohort over time. You can include up to 3 metrics and up to 10 segments.

![](assets/churn-report.png)

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Churn analysis](https://video.tv.adobe.com/v/3430154?quality=12&learn=on&captions=fre_fr){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


### [!UICONTROL Rolling Calculation]

Lets you calculate retention or churn based on the previous column, not the included column.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Latency] Table

Measures the time that has elapsed before and after the inclusion event occurred. This is an excellent tool for pre/post analysis. The **[!UICONTROL Included]** column is in the center of the table and time periods before and after the inclusion event are shown on both sides.

![](assets/cohort-latency.png)

### [!UICONTROL Custom Dimension] Cohort

Create cohorts based on a selected dimension, and not time-based cohorts, which are the default. Use dimensions such as [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region], or any other dimension in Adobe Analytics to show how retention changes based on the different values of these dimensions.

![](assets/cohort-customizable-cohort-row.png)

-->
