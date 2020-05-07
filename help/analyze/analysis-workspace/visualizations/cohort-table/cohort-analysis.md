---
title: Qu’est-ce que l’analyse des cohortes ?
description: En savoir plus sur les analyses de cohortes dans Analyse Workspace
translation-type: tm+mt
source-git-commit: 79849c574909543d74e2935e493008927700585d
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 49%

---


# What is [!UICONTROL Cohort Analysis]?

Une *`cohort`* est un groupe de personnes partageant des caractéristiques communes au cours d’une période spécifique. [!UICONTROL L’analyse des cohortes s’avère utile, par exemple, pour savoir de quelle façon une cohorte réagit par rapport à une marque. ] Vous pouvez facilement déceler des changements de tendances, pour y réagir en conséquence. (Explanations of [!UICONTROL Cohort Analysis] are available on the web, such as at [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

Après avoir créé un rapport de cohorte, vous pouvez en traiter les composants (dimensions, mesures et segments spécifiques), puis partager le rapport avec les personnes de votre choix. Voir  [Traitement et partage](/help/analyze/analysis-workspace/curate-share/curate.md).

Examples of what you can do with [!UICONTROL Cohort Analysis]:

* Lancez des campagnes conçues pour déclencher une action spécifique.
* Ajustez le budget marketing exactement au bon moment au cours du cycle de vie des clients.
* Reconnaître quand terminer un essai ou une offre, afin de maximiser la valeur.
* Trouvez des idées de test A/B dans des domaines tels que le prix, le cheminement de mise à niveau, etc.
* View a [!UICONTROL Cohort Analysis] report within a Guided Analysis report.

[!UICONTROL L’Analyse] de cohortes est disponible pour tous les clients Adobe Analytics disposant de droits d’accès à [!UICONTROL Analyse Workspace].

[Analyse des cohortes sur YouTube](https://www.youtube.com/watch?v=kqOIYrvV-co&amp;index=45&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:36)

>[!IMPORTANT]
>
>[!UICONTROL L’Analyse] de cohortes ne prend pas en charge les mesures non segmentables (y compris les mesures calculées), les mesures non entières (telles que Recettes) ou les occurrences. Seules les mesures pouvant être utilisées dans les segments peuvent être utilisées dans
>[!UICONTROL Cohort Analyse], et elles ne peuvent être incrémentées que de 1 à la fois.

## Fonctions de l’analyse des cohortes

Les fonctionnalités suivantes permettent un contrôle affiné des cohortes que vous créez :

### [!UICONTROL Tableau de rétention]

A [!UICONTROL Retention] cohort report returns visitors: each data cell shows the raw number and percentage of visitors in the cohort who did the action during that time period. Vous pouvez inclure jusqu’à 3 mesures et 10 segments.

![](assets/retention-report.png)

### [!UICONTROL Tableau de perte de clientèle]

A [!UICONTROL Churn] cohort is the inverse of a retention table and shows the visitors who fell out or never met the return criteria for your cohort over time. Vous pouvez inclure jusqu’à 3 mesures et 10 segments.

![](assets/churn-report.png)

### [!UICONTROL Calcul variable]

Permet de calculer la rétention ou la perte de clientèle en fonction de la colonne précédente, et non de la colonne Inclus.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Tableau de latence]

Mesure le temps qui s’est écoulé avant et après l’événement d’inclusion. Il s’agit d’un excellent outil pré-/post-analyse. The **[!UICONTROL Included]** column is in the center of the table and time periods before and after the inclusion event are shown on both sides.

![](assets/cohort-latency.png)

### [!UICONTROL Cohorte de dimension personnalisée]

Créez des cohortes sur la base d’une dimension sélectionnée, et non des cohortes en fonction du temps, qui sont les cohortes par défaut. Use dimensions such as [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region], or any other dimension in Adobe Analytics to show how retention changes based on the different values of these dimensions.

![](assets/cohort-customizable-cohort-row.png)

Pour savoir comment configurer et exécuter un rapport de cohorte, accédez à  [Configuration d’un rapport d’analyse des cohortes](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

