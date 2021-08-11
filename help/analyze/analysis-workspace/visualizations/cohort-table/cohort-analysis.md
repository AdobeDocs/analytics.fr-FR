---
title: Quʼest-ce que lʼanalyse des cohortes et comment fonctionne-t-elle ?
description: Analysez plus précisément les données sur votre audience et triez-les en groupes apparentés grâce à lʼanalyse des cohortes. En savoir plus sur l’analyse des cohortes dans Analysis Workspace.
feature: Visualisations
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: ht
source-wordcount: '491'
ht-degree: 100%

---

# Découvrez [!UICONTROL lʼanalyse des cohortes] dans Adobe Analytics

Une *`cohort`* est un groupe de personnes partageant des caractéristiques communes au cours d’une période spécifique. L’[!UICONTROL analyse des cohortes] s’avère utile, par exemple, pour savoir de quelle façon une cohorte réagit par rapport à une marque. Vous pouvez facilement déceler des changements de tendances, pour y réagir en conséquence. (Vous trouverez des explications sur l’[!UICONTROL analyse des cohortes] sur le Web, tel le cours [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis) (en anglais).)

Après avoir créé un rapport de cohorte, vous pouvez en traiter les composants (dimensions, mesures et segments spécifiques), puis partager le rapport avec les personnes de votre choix. Voir   [Traitement et partage](/help/analyze/analysis-workspace/curate-share/curate.md).

Exemples d’utilisation de l’[!UICONTROL analyse des cohortes] :

* Lancez des campagnes conçues pour déclencher une action spécifique.
* Ajustez le budget marketing exactement au bon moment au cours du cycle de vie des clients.
* Reconnaissez quand terminer un essai ou une offre pour en optimiser la valeur.
* Trouvez des idées de test A/B dans des domaines tels que le prix, le cheminement de mise à niveau, etc.
* Affichez un rapport d’[!UICONTROL analyse des cohortes] au sein d’un rapport d’analyse guidée.

L’[!UICONTROL analyse des cohortes] est disponible pour tous les clients Adobe Analytics avec des droits d’accès à [!UICONTROL Analysis Workspace].

[Tutoriel vidéo sur les analyses des cohortes](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/cohort-analysis-workspace.html?lang=fr) (4:36)

>[!IMPORTANT]
>
>[!UICONTROL Analyse des cohortes]
>
>ne prend pas en charge les mesures qui ne peuvent pas être segmentées (y compris les mesures calculées), les mesures non entières (telles que le chiffre d’affaires) ou les occurrences. Seules les mesures pouvant être utilisées dans les segments peuvent être utilisées dans
>[!UICONTROL l’analyse des cohortes], et elles ne peuvent être incrémentées que de 1 à la fois.

## Capacités de l’analyse des cohortes

Les capacités suivantes vous permettent d’exercer un contrôle précis sur les cohortes que vous créez :

### Tableau de [!UICONTROL rétention]

Un rapport de cohorte de [!UICONTROL rétention] sur les visiteurs récurrents : chaque cellule indique le nombre brut et le pourcentage de visiteurs dans la cohorte qui ont effectué l’action durant cette période. Vous pouvez inclure jusqu’à 3 mesures et 10 segments.

![](assets/retention-report.png)

### Tableau de [!UICONTROL perte de clientèle]

Une cohorte de [!UICONTROL perte de clientèle] est l’inverse d’un tableau de rétention. Elle indique le visiteur qui a abandonné ou n’a jamais rempli les critères de retour de votre cohorte au fil du temps. Vous pouvez inclure jusqu’à 3 mesures et 10 segments.

![](assets/churn-report.png)

### [!UICONTROL Calcul variable]

Permet de calculer la rétention ou la perte de clientèle en fonction de la colonne précédente, et non de la colonne Inclus.

![](assets/cohort-rolling-calculation.png)

### Tableau de [!UICONTROL latence]

Mesure le temps qui s’est écoulé avant et après l’événement d’inclusion. Il s’agit d’un excellent outil pré-/post-analyse. La colonne **[!UICONTROL Inclus]** se trouve au centre du tableau, tandis que les périodes avant et après l’événement d’inclusion sont affichées des deux côtés.

![](assets/cohort-latency.png)

### Cohorte de [!UICONTROL dimension personnalisée]

Créez des cohortes sur la base d’une dimension sélectionnée, et non des cohortes en fonction du temps, qui sont les cohortes par défaut. Utilisez des dimensions telles que le [!UICONTROL canal marketing], la [!UICONTROL campagne], le [!UICONTROL produit], la [!UICONTROL page], la [!UICONTROL région] ou toute autre dimension dans Adobe Analytics de façon à afficher l’évolution de la rétention en fonction des différentes valeurs de ces dimensions.

![](assets/cohort-customizable-cohort-row.png)

Pour savoir comment configurer et exécuter un rapport de cohorte, accédez à   [Configuration d’un rapport d’analyse des cohortes](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).
