---
description: Procédure de création d’une requête de données de base du créateur de rapports.
seo-description: Procédure de création d’une requête de données de base du créateur de rapports.
seo-title: Create a Report Builder data request
solution: Analytics
title: Création d’une requête de données
topic: Créateur de rapports
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Create a Report Builder data request

Procédure de création d’une requête de données de base.

1. In Excel, click **[!UICONTROL Create]**.
1. In the [!UICONTROL Request Wizard: Step 1] window, select a [report suite](../../../analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md#task_59444416F6F042D1998217AE91580913).
1. (Facultatif) Sélectionnez un segment à appliquer à la demande. Quand vous sélectionnez un ou plusieurs segments, ils sont déplacés en haut de la liste.

   Le Créateur de rapports utilise les segments de la même manière qu’Adobe Analytics. Voir le [guide de segmentation d’Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/segment/). 1. (Facultatif) Sélectionnez une liste [de](../../../analyze/report-builder/data-requests/allow-publishing-list-overrides.md#concept_BCB19A20DC4B4B8D984F9670EE018D8C) publication à utiliser pour la distribution.
1. Select a [report type](../../../analyze/report-builder/data-requests/c-report-types/select-report-types.md#concept_C711B27E6FB64C18AC564EE142FC7EFC).
1. Spécifiez une plage [de](../../../analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) dates et une [granularité](../../../analyze/report-builder/data-requests/configuring-report-dates/granularity.md#concept_A13CBA2962E24FF882456135431B7ADB)de rapport.
1. Cliquez sur **[!UICONTROL Suivant]**.
1. In the [Layout - Request Wizard Step 2](../../../analyze/report-builder/layout/layout.md#concept_D66E1C2217E24E1F837AC064C61919DB) window, specify a layout:

   | Élément | Description |
   |---|---|
   | Disposition croisée dynamique | Fournit une grille de lignes, de colonnes et de mesures pour la disposition, comme dans un tableau Excel standard. Cette disposition vous permet d’ajouter des requêtes de ventilation dans une requête d’origine. |
   | Disposition personnalisée | Fournit la plupart des fonctions du paramètre [!UICONTROL Disposition croisée dynamique], mais vous permet, en outre, de choisir l’emplacement de chaque élément de la grille dans la feuille de calcul. Cette disposition offre la même souplesse que dans les versions précédentes. |

1. Sur l’onglet [!UICONTROL Valeurs de mesure], double-cliquez sur les mesures de l’arborescence (ou faites-les glisser) pour les ajouter à la grille [!UICONTROL Valeurs de mesure.]
1. Sur l’onglet [!UICONTROL Dimensions], double-cliquez sur les dimensions (ou faites-les glisser) dans la grille [!UICONTROL Libellés de lignes.]

   Les [dimensions](https://marketing.adobe.com/resources/help/en_US/reference/dimensions.html) disponibles à l’étape 2 dépendent du rapport de base sélectionné à l’étape 1 et de la configuration de votre suite de rapports. Les dimensions sont des éléments qui instaurent une corrélation ou une sous-relation, ou qui sont une classification de la mesure du type de rapport d’origine que vous avez sélectionnée dans la fenêtre [!UICONTROL Assistant Requête : Étape 1]. L’ajout de plusieurs dimensions à l’étape 2 permet de créer une ventilation dans votre requête de données.

   Reportez-vous à la section [Ajout de mesures et de dimensions](../../../analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md#task_E3F520C020F64C5A96DC5C96FEF71FC4) pour plus d’informations.