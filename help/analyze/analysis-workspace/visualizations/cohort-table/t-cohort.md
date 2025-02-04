---
description: Créez une cohorte et générez un rapport d’analyse des cohortes dans Analysis Workspace.
keywords: Analysis Workspace
title: Exécution d’un rapport d’analyse des cohortes
feature: Cohort Analysis
role: User, Admin
exl-id: 523e6f62-b428-454b-9460-6b06e96742c3
source-git-commit: be6056f9e7a64b47ab544594149ebfbe134f1c04
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 34%

---

# Configuration d’une table de cohorte

Pour créer et configurer un [!UICONTROL tableau de cohortes] :

1. Ajoutez une visualisation ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Tableau de cohorte]**. Voir [Ajouter une visualisation à un panneau](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Définissez les **[!UICONTROL critères d’inclusion]**, **[!UICONTROL les critères de retour]**, **[!UICONTROL le type de cohorte]** et **[!UICONTROL les paramètres]** tel qu’illustré dans le tableau ci-dessous.

   ![Configurer un tableau de cohortes](assets/cohort-configure.png)

   | Élément | Description |
   |--- |--- |
   | **[!UICONTROL Critères d’inclusion]** | Vous pouvez appliquer jusqu’à dix filtres d’inclusion et trois mesures d’inclusion. La mesure indique à quelle cohorte appartient un utilisateur. Par exemple, si la mesure d’inclusion est Commandes, seuls les utilisateurs et utilisatrices qui ont passé une commande au cours de la période de l’analyse des cohortes sont inclus dans la cohorte initiale.<br>L’opérateur par défaut entre les mesures est AND, mais vous pouvez le changer en OR. En outre, vous pouvez ajouter un filtrage numérique à ces mesures. Par exemple : `Sessions >= 1`.</br> |
   | **[!UICONTROL Critères de retour]** | Vous pouvez appliquer jusqu’à dix filtres de retour et trois mesures de retour. La mesure indique si l’utilisateur a été fidélisé (rétention) ou non (perte de clientèle). Par exemple, si la mesure de retour est Vues vidéo, seuls les utilisateurs qui ont visionné des vidéos au cours des périodes suivantes (après la période pendant laquelle elles ont été ajoutées à une cohorte) sont représentés comme conservés. Les sessions sont une autre mesure qui quantifie la rétention. |
   | **[!UICONTROL Granularité]** | Granularité temporelle : jour, semaine, mois, trimestre ou année. |
   | **[!UICONTROL Type]** | **[!UICONTROL Rétention]** (par défaut) : une cohorte **[!UICONTROL Rétention]** mesure la façon dont vos cohortes de personnes reviennent sur votre propriété au fil du temps. Une cohorte de rétention est la cohorte standard et indique le comportement de retour et de répétition de l’utilisateur. Une couleur verte indique une cohorte [!UICONTROL Rétention] dans le tableau.<br>**[!UICONTROL Perte de clientèle ]**: une cohorte**[!UICONTROL  Perte de clientèle ]**(également appelée attrition ou abandon) mesure la manière dont vos cohortes de personnes quittent votre propriété au fil du temps. L’attrition est le contraire de la rétention : `Churn = 1 - Retention`. La [!UICONTROL perte de clientèle] est une bonne mesure de l’attractivité et de l’opportunité, car elle vous indique la fréquence à laquelle les clients ne reviennent pas. Vous pouvez utiliser l’attrition pour analyser et identifier les domaines ciblés : quels filtres de cohortes pourraient nécessiter une certaine attention ? Une couleur rouge indique une cohorte [!UICONTROL Perte de clientèle] dans le tableau (similaire à l’abandon dans la visualisation**[!UICONTROL  Flux ]**).</br> |
   | **[!UICONTROL Paramètres]** | **[!UICONTROL Calcul variable]** : calculez la rétention ou l’attrition en fonction de la colonne précédente, plutôt que de la colonne Inclus (par défaut). Le [!UICONTROL calcul variable] change la méthode de calcul pour vos périodes de « retour ». Le calcul normal trouve les utilisateurs qui répondent aux critères de retour et qui faisaient partie de la période d’inclusion. Qu’ils fassent partie ou non de la cohorte de la période précédente. Au lieu de cela, le [!UICONTROL calcul variable] trouve les utilisateurs qui répondent aux critères de « retour » et faisaient partie de la période précédente. Par conséquent, le [!UICONTROL calcul variable] filtre et fait passer par des entonnoirs les utilisateurs qui répondent continuellement aux critères de « retour », période après période. Les critères [!UICONTROL Retour] sont appliqués à chacune des périodes précédant la période sélectionnée. </br><br>**[!UICONTROL Tableau de latence ]**: un [!UICONTROL tableau de latence] mesure le temps écoulé avant et après l’événement d’inclusion. Le [!UICONTROL tableau de latence] est idéal pour une analyse avant/après. Par exemple, vous avez un lancement de produit ou de campagne à venir et vous souhaitez effectuer le suivi du comportement avant et après le lancement. Le [!UICONTROL tableau Latence] affiche côte à côte le comportement avant et après pour voir l’impact direct. Les cellules de pré-inclusion du [!UICONTROL tableau Latence] calculent les utilisateurs qui répondent aux critères [!UICONTROL Inclusion] lors de la période d’inclusion, puis aux critères [!UICONTROL Retour] au cours des périodes précédant la période d’inclusion. Notez que le [!UICONTROL tableau de latence] et la [!UICONTROL cohorte de dimension personnalisée] ne peuvent pas être utilisés ensemble.</br><br>**[!UICONTROL Cohorte de dimension personnalisée]** : créez des cohortes basées sur la dimension sélectionnée plutôt que sur le temps (par défaut). Nombre de clients veulent analyser leurs cohortes en fonction d’autres aspects que le temps. La nouvelle fonctionnalité Cohorte de dimension personnalisée vous fournit la flexibilité de créer des cohortes en fonction des dimensions de votre choix. Utilisez des dimensions telles que le canal marketing, la campagne, le produit, la page, la région ou toute autre dimension pour afficher l’évolution de la rétention en fonction des différentes valeurs de ces dimensions. La définition de filtre de cohorte de [!UICONTROL dimension personnalisée] applique la dimension uniquement dans le cadre de la période d’inclusion, et non dans le cadre de la définition du renvoi.</br><br>Après avoir choisi l’option [!UICONTROL Cohorte de dimension personnalisée], vous pouvez faire glisser et déposer la dimension de votre choix dans la zone de dépôt. L’ajout de dimensions vous permet de comparer des éléments de dimension similaires sur la même période. Vous pouvez par exemple comparer les performances des villes côte à côte, des produits, des campagnes, etc. Le tableau de cohorte renvoie vos 14 principaux éléments de dimension. Cependant, vous pouvez utiliser un filtre ![Filtre](/help/assets/icons/Filter.svg) pour afficher uniquement les éléments de dimension souhaités. Une [!UICONTROL cohorte de dimension personnalisée] ne peut pas être utilisée avec la fonctionnalité [!UICONTROL Tableau de latence].</br> |

1. Cliquez sur **[!UICONTROL Créer]**.
1. Pour reconfigurer le [!UICONTROL tableau de cohortes], sélectionnez ![Modifier](/help/assets/icons/Edit.svg).

1. (Facultatif) Créez un segment à partir d’une sélection.

   Sélectionnez une ou plusieurs cellules (contiguës ou non), puis cliquez avec le bouton droit de la souris > **[!UICONTROL Créer un segment à partir de la sélection]**.


1. Dans le [créateur de segments](/help/components/segmentation/segmentation-workflow/seg-build.md), modifiez davantage le segment, puis cliquez sur **[!UICONTROL Enregistrer]**.

   Le segment enregistré est disponible pour utilisation dans le panneau [!UICONTROL Segment] d’[!UICONTROL Analysis Workspace].

## Paramètres

Vous pouvez définir des paramètres spécifiques pour un [!UICONTROL tableau de cohortes].

1. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) pour ajuster les paramètres du [!UICONTROL Tableau de cohorte].

   | Paramètre | Description |
   |---|---|
   | **Afficher uniquement le pourcentage** | Supprime la valeur numérique et affiche uniquement le pourcentage. |
   | **Arrondir le pourcentage à l’entier le plus proche** | Arrondit la valeur de pourcentage à l’entier le plus proche au lieu d’afficher la valeur décimale. |
   | **Afficher la ligne de pourcentage moyen** | Insère une nouvelle ligne en haut du tableau, puis ajoute la moyenne des valeurs dans chaque colonne. |


>[!MORELIKETHIS]
>
>[Ajouter une visualisation à un panneau](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Paramètres de visualisation ](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu contextuel de visualisation](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

