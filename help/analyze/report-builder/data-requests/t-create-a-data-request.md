---
description: Procédure de création d’une requête de données de base du créateur de rapports.
solution: Analytics
title: Création d’une requête de données
topic: Report builder
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Création d’une requête de données du créateur de rapports

Procédure de création d’une requête de données de base.

1. In Excel, click **[!UICONTROL Create]**.
1. In the [!UICONTROL Request Wizard: Step 1] window, select a [report suite](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Facultatif) Sélectionnez un segment à appliquer à la demande. Quand vous sélectionnez un ou plusieurs segments, ils sont déplacés en haut de la liste.

   Le Créateur de rapports utilise les segments de la même manière qu’Adobe Analytics. Voir le [guide de segmentation d’Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/segment/). 1. (Facultatif) Sélectionnez une liste [de](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md) publication à utiliser pour la distribution.
1. Select a [report type](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Spécifiez une plage [de](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) dates et une [granularité](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md)de rapport.
1. Cliquez sur **[!UICONTROL Suivant]**.
1. In the [Layout - Request Wizard Step 2](/help/analyze/report-builder/layout/layout.md) window, specify a layout:

   | Élément | Description |
   |---|---|
   | Disposition croisée dynamique | Fournit une grille de lignes, de colonnes et de mesures pour la disposition, comme dans un tableau Excel standard. Cette disposition vous permet d’ajouter des requêtes de ventilation dans une requête d’origine. |
   | Disposition personnalisée | Fournit la plupart des fonctions du paramètre [!UICONTROL Disposition croisée dynamique], mais vous permet, en outre, de choisir l’emplacement de chaque élément de la grille dans la feuille de calcul. Cette disposition offre la même souplesse que dans les versions précédentes. |

1. Sur l’onglet [!UICONTROL Valeurs de mesure], double-cliquez sur les mesures de l’arborescence (ou faites-les glisser) pour les ajouter à la grille [!UICONTROL Valeurs de mesure.]
1. Sur l’onglet [!UICONTROL Dimensions], double-cliquez sur les dimensions (ou faites-les glisser) dans la grille [!UICONTROL Libellés de lignes.]

   Les [dimensions](https://marketing.adobe.com/resources/help/en_US/reference/dimensions.html) disponibles à l’étape 2 dépendent du rapport de base sélectionné à l’étape 1 et de la configuration de votre suite de rapports. Les dimensions sont des éléments qui instaurent une corrélation ou une sous-relation, ou qui sont une classification de la mesure du type de rapport d’origine que vous avez sélectionnée dans la fenêtre [!UICONTROL Assistant Requête : Étape 1]. L’ajout de plusieurs dimensions à l’étape 2 permet de créer une ventilation dans votre requête de données.

   Reportez-vous à la section [Ajout de mesures et de dimensions](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) pour plus d’informations.
