---
description: Créez une cohorte et exécutez un rapport d’analyse des cohortes dans Analysis Workspace.
keywords: Analysis Workspace
seo-description: Créez une cohorte et exécutez un rapport d’analyse des cohortes dans Analysis Workspace.
seo-title: Exécution d’un rapport d’analyse des cohortes
solution: Analytics
title: Exécution d’un rapport d’analyse des cohortes
topic: Reports & Analytics
uuid: 5574230f-8f35-43ea-88d6-cb4960ff0bf4
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Configuration d’un rapport d’analyse des cohortes

Créez une cohorte et exécutez un rapport d’analyse des cohortes dans Analysis Workspace.

1. In Analysis Workspace, click the **[!UICONTROL Visualizations]** icon in the left rail and drag a **[!UICONTROL Cohort Table]** to the canvas.

   ![](assets/cohort-table.png)

1. Define the **[!UICONTROL Inclusion Criteria]**, **[!UICONTROL Return Criteria]**, **[!UICONTROL Cohort Type]**, and **[!UICONTROL Settings]** as defined in the table below.

| Élément | Description |
|--- |--- |
| **[!UICONTROL Critères d’inclusion]** | Vous pouvez appliquer jusqu’à dix segments d’inclusion et trois mesures d’inclusion. La mesure spécifie ce qui place un utilisateur dans une cohorte. Par exemple, si la mesure d’inclusion est Commandes, seuls les utilisateurs qui ont passé une commande durant la période de l’analyse des cohortes seront inclus dans la cohorte initiale.<br>L’opérateur par défaut entre les mesures est ET, mais vous pouvez le changer en OU. En outre, vous pouvez ajouter un filtrage numérique à ces mesures. Par exemple : « Visites &gt;= 1 ».</br> |
| **[!UICONTROL Critères de retour]** | Vous pouvez appliquer jusqu’à dix segments de retour et trois mesures de retour. La mesure indique si l’utilisateur a été fidélisé (rétention) ou non (perte de clientèle). Si, par exemple, la mesure de retour est Affichages de vidéos, seuls les utilisateurs qui ont affiché les vidéos durant des périodes consécutives (après la période pendant laquelle ils ont été ajoutés à une cohorte) seront représentés comme fidélisés. La mesure Visites quantifie également la fidélisation des utilisateurs. |
| **[!UICONTROL Granularité]** | Granularité temporelle : jour, semaine, mois, trimestre ou année. |
| **[!UICONTROL Type]** | **** Rétention (par défaut) : une cohorte de rétention mesure si vos cohortes de visiteurs retournent sur votre propriété au cours du temps. Il s’agit de la cohorte standard que nous avons toujours proposé et qui indique le comportement des utilisateurs réguliers et récurrents. Une cohorte de rétention est indiquée par la couleur verte dans le tableau.<br>**[!UICONTROL Churn]**: Une cohorte de visiteurs (également appelée "attrition" ou "abandons") évalue la manière dont vos cohortes de visiteurs abandonnent votre propriété au fil du temps. Perte de clientèle = 1 - rétention. La perte de clientèle est une bonne mesure de l’attractivité et de l’opportunité, car elle vous indique la fréquence à laquelle les clients ne reviennent pas. Vous pouvez utiliser churent pour analyser et identifier les zones ciblées : les segments de cohortes qui pourraient bénéficier d’une certaine attention. A Churn Cohort is indicated by the color red in the table (similar to fallout in our **[!UICONTROL Flow]** visualization).</br> |
| **[!UICONTROL Paramètres]** | **[!UICONTROL Calcul variable]** : calculez la rétention ou la perte de clientèle en fonction de la colonne précédente, plutôt que de la colonne Inclus (par défaut). Le calcul variable change la méthode de calcul pour vos périodes de « retour ». Le calcul normal trouve de manière indépendante les utilisateurs qui répondent aux critères de « retour » et faisaient partie de la période d’inclusion, qu’ils aient ou non fait partie de la cohorte pendant la période précédente. Au lieu de cela, le calcul variable trouve les utilisateurs qui répondent aux critères de « retour » et faisaient partie de la période précédente. Par conséquent, le calcul variable filtre et fait passer par des entonnoirs les utilisateurs qui répondent continuellement aux critères de « retour », période après période. Les critères de retour sont appliqués à chacune des périodes menant à la période sélectionnée. </br><br>**[!UICONTROL Tableau de latence]** : un tableau de latence mesure le temps qui s’est écoulé avant et après l’événement d’inclusion. La latence est très intéressante à utiliser en pré-/post-analyse. Par exemple, si vous avez un lancement de campagne ou de produit à venir et que vous voulez suivre le comportement avant et après, le tableau de latence affiche le comportement avant et après côte à côte afin de voir l’impact direct. Les cellules de préinclusion dans le tableau de latence sont calculées par les utilisateurs qui répondent aux critères d’« inclusion » au cours de la période d’inclusion et répondent ensuite aux critères de « retour » dans les périodes ultérieures à la période d’inclusion. Notez que les tables de latence et la cohorte de dimension personnalisée ne peuvent pas être utilisées conjointement.</br><br>**[!UICONTROL Cohorte de dimension personnalisée]** : créez des cohortes en fonction de la dimension sélectionnée, plutôt qu’en fonction du temps (par défaut). Nombre de clients veulent analyser leurs cohortes en fonction d’autres aspects que le temps. La nouvelle fonctionnalité Cohorte de dimension personnalisée vous fournit la flexibilité de créer des cohortes en fonction des dimensions de votre choix. Utilisez des dimensions telles que le canal marketing, la campagne, le produit, la page, la région ou toute autre dimension dans Adobe Analytics de façon à afficher l’évolution de la rétention en fonction des différentes valeurs de ces dimensions. La définition de segment Dimension de cohorte personnalisée applique la dimension uniquement dans le cadre de la période d’inclusion, et non dans le cadre de la définition du renvoi.</br><br>Après avoir choisi l’option Cohorte de dimension personnalisée, vous pouvez faire glisser et déposer n’importe quelle dimension dans la zone de dépôt. Cela vous permet de comparer des éléments de dimension similaires sur la même période. Par exemple, vous pouvez comparer les performances des villes côte à côte, des produits, des campagnes, etc. Vous verrez vos 14 principaux éléments de dimension. Cependant, vous pouvez utiliser un filtre (accessible en survolant la partie droite de la dimension déposée) pour afficher uniquement les éléments de dimension désirés. Une cohorte de dimension personnalisée ne peut pas être utilisée avec la fonctionnalité de tableau de latence.</br> |

1. Réglez les paramètres **[!UICONTROL du tableau de]** cohortes en cliquant sur l’icône d’engrenage.

| Paramètre| Description|| Afficher uniquement le pourcentage| Supprime la valeur numérique et affiche uniquement le pourcentage. || Pourcentage arrondi au plus proche entier| Arrondit le pourcentage à la valeur entière la plus proche au lieu d'afficher la valeur décimale. || Afficher la rangée en pourcentage moyen| Insère une nouvelle ligne en haut du tableau, puis ajoute la moyenne des valeurs de chaque colonne. |

## Création du rapport Analyse des cohortes

1. Cliquez sur **[!UICONTROL Créer]**.

   ![Résultat de l’étape](assets/cohort-report.png)

   Le rapport montre les visiteurs qui ont passé une commande ( *`Included`* colonne) et qui sont revenus sur votre site lors de visites ultérieures. Une réduction des visites au fil du temps permet d’identifier les problèmes et d’agir.
1. (Facultatif) Créez un segment à partir d’une sélection.

   Sélectionnez des cellules (contiguës ou non), puis cliquez avec le bouton droit de la souris &gt; **[!UICONTROL Créer un segment d’après la sélection]**.

1. In the [Segment Builder](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html), further edit the segment, then click **[!UICONTROL Save]**.

   Le segment enregistré est disponible pour utilisation dans le panneau [!UICONTROL Segment] d’Analysis Workspace.
1. Nommez et enregistrez votre projet de cohorte.
1. (Optional) [Curate and share](../../../../analyze/analysis-workspace/curate-share/curate.md#concept_4A9726927E7C44AFA260E2BB2721AFC6) the project components.

   >[!NOTE]
   >
   >Vous devez enregistrer votre projet avant que le traitement ne soit disponible.

