---
description: Procédure d’ajout de mesures et de dimensions à une requête.
title: Ajout de mesures et de dimensions
topic: Report builder
uuid: 588ce96b-3a2d-42b7-8a8e-7e6f448a0115
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Ajout de mesures et de dimensions

Procédure d’ajout de mesures et de dimensions à une requête.

1. [Créez la requête](/help/analyze/report-builder/data-requests/data-requests.md) de données sur le [!UICONTROL Request Wizard: Step 1], puis cliquez sur **[!UICONTROL Next]**.
1. On the [!UICONTROL Request Wizard: Step 2], double-click metrics, or drag them to the desired position.

   ![Infos sur l’étape](assets/adding_metrics.png)

   When you add metrics, they are not removed from the [!UICONTROL Metrics] tab, because you can display metrics multiple times within a request. Vous pouvez, par exemple, afficher le sous-total de la mesure en plus de chaque valeur. Cependant, la liste des mesures disponibles est modifiée chaque fois que vous ajoutez ou supprimez une dimension.

   You can add only metrics to the [!UICONTROL Metrics] layout section. Les mesures sont ajoutées à la [!UICONTROL Column Label] mise en page sous forme [!UICONTROL Metric Header]. If you move a [!UICONTROL Metric Header] from [!UICONTROL Column Layout] to [!UICONTROL Row Layout], it is displayed there and is used as a metric as a breakdown.

   Une barre de recherche s’affiche sur l’onglet Mesures, juste au-dessus de la liste Mesure.

   ![](assets/search_bar_metric.png)

   N’oubliez pas ce qui suit :

   * Quand vous entrez un terme à rechercher, la liste est automatiquement mise à jour afin d’afficher uniquement les mesures dont l’intitulé correspond au terme recherché.
   * Le résultat ne tient pas respect de la casse et équivaut à une recherche « contient ».
   * Les recherches de mots complets ou autres indicateurs de recherche (commence par, se termine par, ET, OU, etc.) ne sont pas prises en charge.

      Le terme recherché sera effacé si vous quittez l’Assistant Requête (c.-à-d. Terminer ou Annuler) ou revenez à la première étape de l’Assistant Requête ou modifiez la catégorie de mesure.

      Le terme recherché ne sera pas effacé dans les cas suivants :

   * Vous faites glisser et déplacez (ou double-cliquez) l’un des éléments de mesure de la liste afin de l’ajouter au panneau Mesures Disposition croisée dynamique/Disposition personnalisée.
   * Vous supprimez un ou plusieurs éléments de mesure du panneau Mesures Disposition croisée dynamique/Disposition personnalisée.
   * Vous cliquez sur l’onglet Dimension, puis revenez à l’onglet Mesure.
   * Vous invoquez d’autres formulaires secondaires (modaux ou sans mode) qui à leur fermeture renvoient vers la deuxième étape de l’Assistant Requête. Exemple de ces formulaires :

      * Formulaires de filtre de dimension
      * Formulaires de mise en forme de la plage de sortie
      * Formulaire d’options de format
      * Formulaire Ajouter un texte en préfixe/suffixe
      * Formulaire d’emplacement de la plage de sortie

1. (Facultatif) Pour trier une requête par mesure, cliquez simplement sur le libellé de la mesure.
1. Pour ajouter des dimensions, procédez de la même manière que pour des mesures.

Dans l’onglet [!UICONTROL Dimensions], le système affiche les dimensions qui ventilent tout rapport de base sélectionné à l’étape 1, ou qui en sont une classification, et sur la configuration de la suite de rapports. Lorsque vous déposez une dimension sur les grilles de disposition, elle est supprimée de l’arborescence et elle recalcule la liste des dimensions restantes disponibles.

La dimension [!UICONTROL Date] est ajoutée automatiquement. Available date dimensions change depending on the selected granularity from the [!UICONTROL Request Wizard: Step 1]. (Les valeurs valides sont :

    * Heure
    * Jour
    * Semaine
    * Mois
    * Année
    * Plage de dates (lorsqu’aucune granularité n’est spécifiée)

1. Modifiez les mesures et les dimensions en configurant les [options de format](/help/analyze/report-builder/layout/t-format-display-headers.md) et les filtres.
1. Cliquez sur **[!UICONTROL Finish]**.
Dans l’exemple suivant, des dimensions sont en relation avec la mesure [!UICONTROL Page]. Ici, la [!UICONTROL Referring Domain] dimension crée un rapport de ventilation entre [!UICONTROL Page] et [!UICONTROL Referring Domain]. L’onglet [!UICONTROL Dimension] est mis à jour avec les seules dimensions que vous pouvez ajouter à un rapport de ventilation.

![](assets/page_pageview_02.png)
