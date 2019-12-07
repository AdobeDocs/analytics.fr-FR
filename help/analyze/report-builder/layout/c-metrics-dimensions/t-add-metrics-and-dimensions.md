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

1. [Créez la requête de données](/help/analyze/report-builder/data-requests/data-requests.md) dans le formulaire [!UICONTROL Assistant Requête : Étape 1], puis cliquez sur **[!UICONTROL Suivant]**.
1. Dans le formulaire [!UICONTROL Assistant Requête : Étape 2], double-cliquez sur les mesures ou faites-les glisser vers l’emplacement de votre choix.

   ![Infos sur l’étape](assets/adding_metrics.png)

   Les mesures que vous ajoutez ne sont pas supprimées de l’onglet [!UICONTROL Valeurs de mesure], car vous pouvez les afficher plusieurs fois dans une requête. Vous pouvez, par exemple, afficher le sous-total de la mesure en plus de chaque valeur. Cependant, la liste des mesures disponibles est modifiée chaque fois que vous ajoutez ou supprimez une dimension.

   Vous pouvez uniquement ajouter des mesures à la section de disposition [!UICONTROL Valeurs de mesure]. Les mesures sont ajoutées à la disposition [!UICONTROL Libellé de colonne] sous forme d’[!UICONTROL En-tête de mesure]. Si vous déplacez un [!UICONTROL En-tête de mesure] depuis la [!UICONTROL Disposition de colonne] vers la [!UICONTROL Disposition de ligne], elle est affichée à cet endroit et utilise la mesure sous la forme d’une ventilation.

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

La dimension [!UICONTROL Date] est ajoutée automatiquement. Les dimensions de date disponibles varient en fonction de la granularité sélectionnée dans le formulaire [!UICONTROL Assistant Requête : Étape 1]. (Les valeurs valides sont :

    * Heure
    * Jour
    * Semaine
    * Mois
    * Année
    * Période (lorsqu’aucune granularité n’est spécifiée)

1. Modifiez les mesures et les dimensions en configurant les options [de](/help/analyze/report-builder/layout/t-format-display-headers.md) format et les filtres.
1. Cliquez sur **[!UICONTROL Terminer]**.
Dans l’exemple suivant, des dimensions sont en relation avec la mesure [!UICONTROL Page]. Dans le cas présent, la dimension [!UICONTROL Domaine référent] crée un rapport de ventilation entre celui-ci et [!UICONTROL Page]. L’onglet [!UICONTROL Dimension] est mis à jour avec les seules dimensions que vous pouvez ajouter à un rapport de ventilation.

![](assets/page_pageview_02.png)
