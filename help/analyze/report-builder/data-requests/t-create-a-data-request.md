---
description: Procédure de création d’une requête de données avec le Report Builder.
title: Création d’une requête de données
topic: Report builder
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Création d’une requête de données dans le Report Builder

Procédure de création d’une requête de données de base.

1. In Excel, click **[!UICONTROL Create]**.
1. Dans la [!UICONTROL Request Wizard: Step 1] fenêtre, sélectionnez une suite [de](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)rapports.
1. (Facultatif) Sélectionnez un segment à appliquer à la demande. Quand vous sélectionnez un ou plusieurs segments, ils sont déplacés en haut de la liste.

   Le Report Builder utilise les segments de la même manière qu’Adobe Analytics. Voir le [guide de segmentation d’Analytics](https://marketing.adobe.com/resources/help/fr_FR/analytics/segment/). 1. (Facultatif) Sélectionnez une [liste de publication](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md) à utiliser pour la distribution.
1. Sélectionnez un [type de rapport](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Spécifiez une [plage de dates](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) et une [granularité](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md) de rapport.
1. Cliquez sur **[!UICONTROL Next]**.
1. Dans la fenêtre [Disposition - Assistant Requête : Étape 2](/help/analyze/report-builder/layout/layout.md), sélectionnez une disposition :

   | Élément | Description |
   |---|---|
   | Disposition croisée dynamique | Fournit une grille de lignes, de colonnes et de mesures pour la disposition, comme dans un tableau Excel standard. Cette disposition vous permet d’ajouter des requêtes de ventilation dans une requête d’origine. |
   | Disposition personnalisée | Provides most of the functionality of the [!UICONTROL Pivot Layout] but lets you choose where each item in the grid should be located in the spreadsheet. Cette disposition offre la même souplesse que dans les versions précédentes. |

1. On the [!UICONTROL Metrics] tab, double-click (or drag) metrics in the tree to add them to the [!UICONTROL Metrics] grid.
1. On the [!UICONTROL Dimensions] tab, double-click (or drag) dimensions to the [!UICONTROL Row Labels] grid.

   Les [dimensions](https://marketing.adobe.com/resources/help/fr_FR/reference/dimensions.html) disponibles à l’étape 2 dépendent du rapport de base sélectionné à l’étape 1 et de la configuration de votre suite de rapports. The dimensions are items that correlate, sub-relate, or are a classification of the original report type metric you selected on the [!UICONTROL Request Wizard: Step 1] window. L’ajout de plusieurs dimensions à l’étape 2 permet de créer une ventilation dans votre requête de données.

   Reportez-vous à la section [Ajout de mesures et de dimensions](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) pour plus d’informations.
