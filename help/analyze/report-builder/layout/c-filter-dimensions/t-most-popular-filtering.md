---
description: Classement et filtres conditionnels pouvant être configurés à l’aide d’une logique booléenne et d’expressions de recherche ET/OU.
title: Filtrage le plus apprécié
topic: Report builder
uuid: 558fa592-41be-4e66-8705-81262afe1fc7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filtrage le plus apprécié

Classement et filtres conditionnels pouvant être configurés à l’aide d’une logique booléenne et d’expressions de recherche ET/OU.

Les les plus populaires sont    que vous configurez à l’aide d’une logique booléenne avec des conditions ET/OU, comme [!UICONTROL Page does not contain]*`<product name>`* avec des conditions ou des groupes de conditions comme [!UICONTROL Includes All], [!UICONTROL Includes Any]ou [!UICONTROL Excludes All]. Vous pouvez [enregistrer](/help/analyze/report-builder/layout/c-filter-dimensions/saved-filters.md) ces expressions pour une autre requête dans ce classeur ou dans d’autres classeurs.

**Pour créer un filtre de type « Le plus populaire »**

1. Créez ou modifiez une requête, puis accédez au dossier [!UICONTROL Request Wizard: Step 2].

   ![Infos sur l’étape](assets/dimension_filter.png)

1. On the [!UICONTROL Request Wizard: Step 2], click the link next to the dimension in the grid, then choose **[!UICONTROL Filter]**.
1. Dans le [!UICONTROL Choose Page] formulaire, activez **[!UICONTROL Most Popular]**, puis configurez les options suivantes :

   **Ordre de classement** : il s’agit de l’ordre de classement d’une dimension. La valeur par défaut, à savoir 1, indique l’élément supérieur dans la liste des données faisant l’objet du rapport. Par exemple, dans le cas de la dimension [!UICONTROL Page], un ordre de classement de 1 indique la page la plus demandée de votre site. Vous pouvez spécifier 10 ou une autre valeur comme cellule d’ordre de classement, ce qui a pour effet de générer un rapport commençant par 10 comme valeur maximale. Les mesures sont classées par ordre décroissant, de telle sorte que les éléments les plus actifs apparaissent en premier dans la liste. Si une seule requête doit comporter plus de 50 000 noms de pages, mais que vous disposez de milliers de pages sur lesquelles générer un rapport, vous pouvez copier la requête et modifier l’ordre de classement afin de récupérer les données appropriées par blocs de 50 000.

   **Nombre d’entrées :** ( [!UICONTROL Pivot Layout] uniquement) Définit le nombre d’éléments signalés pour une mesure spécifique au cours d’une période donnée. Certaines mesures peuvent répertorier une centaine d’entrées, alors que d’autres n’en afficheront que quelques-unes. For example, for the dimension [!UICONTROL Site Section], a number of entries of 25 indicates that the report shows the 25 most visited pages.

   Les flèches vous permettent de modifier le [!UICONTROL Starting Rank] et [!UICONTROL Number of Entries] le premier point de données de la feuille. Par défaut, la valeur [!UICONTROL Starting Rank] est 1 et la valeur [!UICONTROL Number of Entries] 10. Ces valeurs peuvent être ajustées d’un minimum à un maximum de 50 000 pour certaines mesures. Chaque mesure a son propre plafond [!UICONTROL Number of Entries]. Ces champs n’acceptent pas les valeurs négatives ou nulles. If you choose a [!UICONTROL Starting Rank] as 15 and [!UICONTROL Number of Entries] as 10, data requests for the metric return the 10 most visited pages, where the first most visited page is number 15 in the list for the specific date range. Toutes les pages les plus demandées classées entre la 15ème et la 25ème positions sont répertoriées dans l’ordre décroissant.

   >[!NOTE]
   >
   >L’application de filtres à des requêtes existantes entraîne la modification des données présentées. Supposons que vous ayez mappé les dix premiers [!UICONTROL Pages] aux cellules $A$1 à $A$10, avec 1 pour [!UICONTROL Starting Rank] et 10 pour [!UICONTROL Number of Entries]. If you change these values to show 1 for [!UICONTROL Starting Rank] and only 3 for [!UICONTROL Number of Entries], the data previously filling cells $A$4 through $A$10 will no longer appear.

1. To create a search expression, click **[!UICONTROL Add]**.

   ![Infos sur l’étape](assets/expressions_define_filter.png)

1. On the [!UICONTROL Define Filter] form, configure the conditions appropriate for your needs.

   ![select_cell_icon.png](assets/select_cell_icon.png) : vous permet de localiser une condition définie dans la valeur d’une cellule.

   **Ajouter une condition** : ajoute une condition à l’expression. Le nombre de conditions qu’il est possible d’ajouter est illimité.

1. Cliquez sur **[!UICONTROL OK]**.

   ![Infos sur l’étape](assets/choose_page_02.png)

1. Sur le [!UICONTROL Choose Page] formulaire, cliquez **[!UICONTROL Save]** pour enregistrer le  .
1. Cliquez sur **[!UICONTROL OK]**.
