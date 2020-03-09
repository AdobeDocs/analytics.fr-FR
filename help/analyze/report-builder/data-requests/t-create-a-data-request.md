---
description: Procédure de création d’une requête de données avec le Report Builder.
title: Création d’une requête de données
topic: Report builder
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Création d’une requête de données dans le Report Builder

Procédure de création d’une requête de données de base.

1. Dans Excel, cliquez sur **[!UICONTROL Créer]**.
1. Dans la fenêtre [!UICONTROL Assistant Requête : Étape 1], sélectionnez une [suite de rapports](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Facultatif) Sélectionnez un segment à appliquer à la demande. Quand vous sélectionnez un ou plusieurs segments, ils sont déplacés en haut de la liste.

   Le Report Builder utilise les segments de la même manière qu’Adobe Analytics. Voir le [guide de segmentation d’Analytics](https://marketing.adobe.com/resources/help/fr_FR/analytics/segment/). 1. (Facultatif) Sélectionnez une [liste de publication](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md) à utiliser pour la distribution.
1. Sélectionnez un [type de rapport](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Spécifiez une [plage de dates](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) et une [granularité](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md) de rapport.
1. Cliquez sur **[!UICONTROL Suivant]**.
1. Dans la fenêtre [Disposition - Assistant Requête : Étape 2](/help/analyze/report-builder/layout/layout.md), sélectionnez une disposition :

   | Élément | Description |
   |---|---|
   | Disposition croisée dynamique | Fournit une grille de lignes, de colonnes et de mesures pour la disposition, comme dans un tableau Excel standard. Cette disposition vous permet d’ajouter des requêtes de ventilation dans une requête d’origine. |
   | Disposition personnalisée | Fournit la plupart des fonctions du paramètre [!UICONTROL Disposition croisée dynamique], mais vous permet, en outre, de choisir l’emplacement de chaque élément de la grille dans la feuille de calcul. Cette disposition offre la même souplesse que dans les versions précédentes. |

1. Sur l’onglet [!UICONTROL Valeurs de mesure], double-cliquez sur les mesures de l’arborescence (ou faites-les glisser) pour les ajouter à la grille [!UICONTROL Valeurs de mesure].
1. Sur l’onglet [!UICONTROL Dimensions], double-cliquez sur les dimensions (ou faites-les glisser) dans la grille [!UICONTROL Libellés de lignes].

   Les [dimensions](https://marketing.adobe.com/resources/help/fr_FR/reference/dimensions.html) disponibles à l’étape 2 dépendent du rapport de base sélectionné à l’étape 1 et de la configuration de votre suite de rapports. Les dimensions sont des éléments qui instaurent une corrélation ou une sous-relation, ou qui sont une classification de la mesure du type de rapport d’origine que vous avez sélectionnée dans la fenêtre [!UICONTROL Assistant Requête : Étape 1]. L’ajout de plusieurs dimensions à l’étape 2 permet de créer une ventilation dans votre requête de données.

   Reportez-vous à la section [Ajout de mesures et de dimensions](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) pour plus d’informations.
