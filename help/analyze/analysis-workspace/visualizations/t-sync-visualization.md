---
description: Synchronisez les visualisations pour contrôler quel tableau de données ou source de données correspond à une visualisation.
keywords: Analysis Workspace;Synchronize visualization with data source
title: Gestion des sources de données
translation-type: tm+mt
source-git-commit: 6eda9e3e5bd450213253a8181042c24c318c0300

---


# Gestion des sources de données

Synchronisez les visualisations pour contrôler quel tableau de données ou source de données correspond à une visualisation.

**Conseil :** Vous pouvez savoir quelles visualisations sont liées d’après la couleur du point près du titre. Les couleurs correspondantes signifient que les visualisations reposent sur la même source de données.

La gestion d’une source de données permet d’afficher la source de données ou de verrouiller la sélection. Ces paramètres déterminent la manière dont la visualisation change (ou ne change pas) lorsque de nouvelles données arrivent.

1. [Créez un projet](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md) avec un tableau de données et une [visualisation](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. Dans le tableau de données, sélectionnez les cellules (source de données) à associer à la visualisation.
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. Sélectionnez **[!UICONTROL Show Data Source]** ou **[!UICONTROL Lock Selection]**.

   ![](assets/manage-data-source.png)

   La synchronisation d’une visualisation sur une cellule de tableau crée un nouveau tableau (masqué) et code par couleur la visualisation synchronisée avec ce tableau.

| Elément | Description |
|--- |--- |
| Visualisations liées | Si des visualisations sont connectées à un tableau à structure libre ou de cohortes, le point supérieur gauche répertorie les visualisations connectées, accompagnées d’une case à cocher « Afficher » qui permet d’afficher ou de masquer le tableau.  Le survol met en surbrillance la visualisation liée et le fait de cliquer dessus vous amène à la visualisation. |
| Afficher la source de données | Permet d’afficher (en activant la case à cocher) ou de masquer (en désactivant) le tableau de données qui correspond à la visualisation. |
| Verrouiller la sélection | Activez ce paramètre pour verrouiller la visualisation sur les données actuellement sélectionnées dans le tableau de données correspondant. Une fois activé, choisissez entre :  <ul><li>**Positions** sélectionnées : Sélectionnez cette option si vous souhaitez que la visualisation reste verrouillée sur les positions sélectionnées dans le tableau de données correspondant. Ces positions continueront à être visualisées, même si les éléments spécifiques de ces positions changent. Par exemple, sélectionnez cette option si vous souhaitez afficher les cinq premiers noms de campagne en tout temps dans cette visualisation, quels que soient les noms de campagne qui apparaissent dans les cinq premiers.</li> <li>**Eléments** sélectionnés : Sélectionnez cette option si vous souhaitez que la visualisation reste verrouillée sur les éléments spécifiques actuellement sélectionnés dans le tableau de données correspondant. Ces éléments continueront à être visualisés, même s’ils changent leur classement parmi les éléments du tableau. Par exemple, sélectionnez cette option si vous souhaitez afficher les cinq mêmes noms de campagne spécifiques à tout moment dans cette visualisation, quel que soit le classement de ces noms de campagne.</li></ul> |

Cette nouvelle architecture diffère de la précédente du fait qu’Analysis Workspace ne crée plus de tableau masqué en double où est automatiquement stockée la sélection verrouillée. Désormais, la source de données pointe vers le tableau à partir duquel vous avez créé la visualisation.

**Exemples d’utilisation :**

* Créez une visualisation de synthèse et verrouillez-la sur une cellule du tableau à partir duquel elle a été créée. Si l’option Afficher la source de données est activée, vous savez exactement d’où proviennent ces informations dans le tableau. Les données source seront grisées :

   ![](assets/data-source2.png)>
* Vous pouvez ajouter de nombreuses visualisations dont les données sont issues de différentes cellules du même tableau, comme illustré ici. Le tableau est identique à celui de l’exemple ci-dessus, mais la cellule source (et la mesure) est différente :

   ![](assets/data-source3.png)>
* Vous pouvez déterminer s’il existe des visualisations liées à un tableau à structure libre ou à un tableau de cohortes en cliquant sur le point supérieur gauche (Paramètres de source de données). Le survol met en surbrillance la visualisation liée, et cliquer dessus vous y mènera.

   ![](assets/linked-visualizations.png)>
