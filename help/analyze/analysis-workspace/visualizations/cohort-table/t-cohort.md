---
description: Créez une cohorte et générez un rapport d’analyse des cohortes dans Analysis Workspace.
keywords: Analysis Workspace
title: Exécution d’un rapport d’analyse des cohortes
topic: Reports and analytics
uuid: 5574230f-8f35-43ea-88d6-cb4960ff0bf4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Configuration d’un rapport d’analyse des cohortes

Créez une cohorte et générez un rapport d’analyse des cohortes dans Analysis Workspace.

1. In Analysis Workspace, click the **[!UICONTROL Visualizations]** icon in the left rail and drag a **[!UICONTROL Cohort Table]** to the canvas.

   ![](assets/cohort-table.png)

1. Définissez le **[!UICONTROL Inclusion Criteria]**, **[!UICONTROL Return Criteria]**, **[!UICONTROL Cohort Type]** et **[!UICONTROL Settings]** comme défini dans le tableau ci-dessous.

| Élément | Description |
|--- |--- |
| **[!UICONTROL Inclusion Criteria]** | Vous pouvez appliquer jusqu’à dix segments d’inclusion et trois mesures d’inclusion. La mesure spécifie ce qui place un utilisateur dans une cohorte. Par exemple, si la mesure d’inclusion est Commandes, seuls les utilisateurs qui ont passé une commande durant la période de l’analyse des cohortes seront inclus dans la cohorte initiale.<br>L’opérateur par défaut entre les mesures est AND, mais vous pouvez le changer en OR. En outre, vous pouvez ajouter un filtrage numérique à ces mesures. Par exemple : « Visites >= 1 ».</br> |
| **[!UICONTROL Return Criteria]** | Vous pouvez appliquer jusqu’à dix segments de retour et trois mesures de retour. La mesure indique si l’utilisateur a été fidélisé (rétention) ou non (perte de clientèle). Si, par exemple, la mesure de retour est Affichages de vidéos, seuls les utilisateurs qui ont affiché les vidéos durant des périodes consécutives (après la période pendant laquelle ils ont été ajoutés à une cohorte) seront représentés comme fidélisés. La mesure Visites quantifie également la fidélisation des utilisateurs. |
| **[!UICONTROL Granularity]** | Granularité temporelle : jour, semaine, mois, trimestre ou année. |
| **[!UICONTROL Type]** | **[!UICONTROL Retention]**(par défaut) : Une cohorte de fidélisation évalue la mesure dans laquelle les cohortes de retournent à votre propriété au fil du temps. Il s’agit de la cohorte standard que nous avons toujours proposé et qui indique le comportement des utilisateurs réguliers et récurrents. Une cohorte de rétention est indiquée par la couleur verte dans le tableau.<br>**[!UICONTROL Churn]**: Une cohorte d’abandon (également appelée &quot;attrition&quot; ou &quot;abandon&quot;) évalue la manière dont vos cohortes d’abandonnent votre propriété au fil du temps. Perte de clientèle = 1 - rétention. La perte de clientèle est une bonne mesure de l’attractivité et de l’opportunité, car elle vous indique la fréquence à laquelle les clients ne reviennent pas. Vous pouvez utiliser la perte de clientèle pour analyser et identifier les zones d’intérêt, c’est-à-dire les segments de cohortes qui pourraient avoir besoin d’attention. A Churn Cohort is indicated by the color red in the table (similar to fallout in our **[!UICONTROL Flow]** visualization).</br> |
| **[!UICONTROL Settings]** | **[!UICONTROL Rolling Calculation]**: Calculez la rétention ou la perte de clientèle d’après la colonne précédente, plutôt que d’après la colonne Inclus (par défaut). Le calcul variable change la méthode de calcul pour vos périodes de « retour ». Le calcul normal trouve de manière indépendante les utilisateurs qui répondent aux critères de « retour » et faisaient partie de la période d’inclusion, qu’ils aient ou non fait partie de la cohorte pendant la période précédente. Au lieu de cela, le calcul variable trouve les utilisateurs qui répondent aux critères de « retour » et faisaient partie de la période précédente. Par conséquent, le calcul variable filtre et fait passer par des entonnoirs les utilisateurs qui répondent continuellement aux critères de « retour », période après période. Les critères de retour sont appliqués à chacune des périodes menant à la période sélectionnée. </br><br>**[!UICONTROL Latency Table]**: Un tableau de latence mesure la durée écoulée avant et après que l’événement d’inclusion ne se produise. La latence est très intéressante à utiliser en pré-/post-analyse. Par exemple, si vous avez un lancement de campagne ou de produit à venir et que vous voulez suivre le comportement avant et après, le tableau de latence affiche le comportement avant et après côte à côte afin de voir l’impact direct. Les cellules de préinclusion dans le tableau de latence sont calculées par les utilisateurs qui répondent aux critères d’« inclusion » au cours de la période d’inclusion et répondent ensuite aux critères de « retour » dans les périodes ultérieures à la période d’inclusion. Notez que les tables de latence et la cohorte de dimension personnalisée ne peuvent pas être utilisées conjointement.</br><br>**[!UICONTROL Custom Dimension Cohort]**: Créez des cohortes d’après la dimension sélectionnée, plutôt que d’après les cohortes en fonction du temps (par défaut). Nombre de clients veulent analyser leurs cohortes en fonction d’autres aspects que le temps. La nouvelle fonctionnalité Cohorte de dimension personnalisée vous fournit la flexibilité de créer des cohortes en fonction des dimensions de votre choix. Utilisez des dimensions telles que le canal marketing, la campagne, le produit, la page, la région ou toute autre dimension dans Adobe Analytics de façon à afficher l’évolution de la rétention en fonction des différentes valeurs de ces dimensions. La définition de segment Dimension de cohorte personnalisée applique la dimension uniquement dans le cadre de la période d’inclusion, et non dans le cadre de la définition du renvoi.</br><br>Après avoir choisi l’option Cohorte de dimension personnalisée, vous pouvez faire glisser et déposer n’importe quelle dimension dans la zone de dépôt. Cela vous permet de comparer des éléments de dimension similaires sur la même période. Par exemple, vous pouvez comparer les performances des villes côte à côte, des produits, des campagnes, etc. Vous verrez vos 14 principaux éléments de dimension. Cependant, vous pouvez utiliser un filtre (accessible en survolant la partie droite de la dimension déposée) pour afficher uniquement les éléments de dimension désirés. Une cohorte de dimension personnalisée ne peut pas être utilisée avec la fonctionnalité de tableau de latence.</br> |

1. Réglez le **[!UICONTROL Cohort Table Settings]** en cliquant sur l’icône d’engrenage.

| Paramètre| Description|
| Afficher uniquement le pourcentage | Supprime la valeur numérique et affiche uniquement le pourcentage. |
| Pourcentage arrondi au plus proche entier | Arrondit le pourcentage à la valeur entière la plus proche au lieu d’afficher la valeur décimale. |
| Afficher la rangée en pourcentage moyen | Insère une nouvelle ligne en haut du tableau, puis ajoute la moyenne des valeurs dans chaque colonne. |

## Création du rapport Analyse des cohortes

1. Cliquez sur **[!UICONTROL Build]**.

   ![Résultat de l’étape](assets/cohort-report.png)

   Le rapport présente les visiteurs qui ont passé une commande (colonne *`Included`*) et qui sont revenus sur votre site au cours de visites consécutives. Une réduction des visites au fil du temps permet d’identifier les problèmes et d’agir.
1. (Facultatif) Créez un segment à partir d’une sélection.

   Sélectionnez des cellules (contiguës ou non contiguës), puis cliquez avec le bouton droit de la souris > **[!UICONTROL Create Segment From Selection]**.

1. In the [Segment Builder](https://marketing.adobe.com/resources/help/fr_FR/analytics/segment/seg_build.html), further edit the segment, then click **[!UICONTROL Save]**.

   Le enregistré est disponible pour utilisation dans le panneau [!UICONTROL Segment]Segment d’Analysis Workspace.
1. Nommez et enregistrez votre projet de cohorte.
1. (Facultatif) [Traitez et partagez](/help/analyze/analysis-workspace/curate-share/curate.md) les composants de projet.

   >[!NOTE]
   >
   >Vous devez enregistrer votre projet pour que la fonction de traitement soit disponible.

