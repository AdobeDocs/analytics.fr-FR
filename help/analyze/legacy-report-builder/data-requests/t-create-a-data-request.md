---
description: Procédure de création d’une requête de données avec le Report Builder.
title: Création d’une requête de données
feature: Report Builder
role: User, Admin
exl-id: 21d552a0-7a58-4217-ba8a-7c87eb4757f6
TQID: https://experienceleague.adobe.com/w-oiIfs1qFMoQbaN8YrNIn1TRNHeN97lQOlkLeXdLb0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 284
ht-degree: 50%

---

# Création d’une requête de données dans le Report Builder

{{legacy-arb}}

Procédure de création d’une requête de données de base.

1. Dans Excel, cliquez sur **[!UICONTROL Créer]**.
1. Dans la fenêtre [!UICONTROL Assistant Requête : Étape 1], sélectionnez une [suite de rapports](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Facultatif) Sélectionnez un segment à appliquer à la demande. Quand vous sélectionnez un ou plusieurs segments, ils sont déplacés en haut de la liste.

   Le Report Builder utilise les segments de la même manière qu’Adobe Analytics. Voir le [guide de segmentation d’Analytics](/help/components/segmentation/seg-home.md).
1. Sélectionnez un [type de rapport](/help/analyze/legacy-report-builder/data-requests/c-report-types/select-report-types.md).
1. Spécifiez une [plage de dates](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md) et une [granularité](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/granularity.md) de rapport.
1. Cliquez sur **[!UICONTROL Suivant]**.
1. Dans la fenêtre [Disposition - Assistant Requête : Étape 2](/help/analyze/legacy-report-builder/layout/layout.md), sélectionnez une disposition :

   | Élément | Description |
   |---|---|
   | Disposition du tableau croisé dynamique | Fournit une ligne, une colonne et une grille de mesures pour la mise en page, comme pour les tableaux Excel standard. Cette disposition permet d’ajouter des requêtes de répartition dans une requête d’origine. |
   | Disposition personnalisée | Fournit la plupart des fonctionnalités de la [!UICONTROL disposition du tableau croisé dynamique] mais vous permet de choisir l&#39;emplacement de chaque élément de la grille dans la feuille de calcul. Cette disposition offre la flexibilité disponible dans les versions précédentes. |

1. Sur l’onglet [!UICONTROL Valeurs de mesure], double-cliquez sur les mesures de l’arborescence (ou faites-les glisser) pour les ajouter à la grille [!UICONTROL Valeurs de mesure].
1. Sur l’onglet [!UICONTROL Dimensions], double-cliquez sur les dimensions (ou faites-les glisser) dans la grille [!UICONTROL Libellés de lignes].

   Les [dimensions](/help/analyze/report-builder/filter-dimensions.md) disponibles à l’étape 2 dépendent du rapport de base que vous avez sélectionné à l’étape 1, ainsi que de la configuration de votre suite de rapports. Les dimensions sont des éléments qui sont en corrélation, en sous-relation ou sont une classification de la mesure de type de rapport d’origine que vous avez sélectionnée dans la fenêtre [!UICONTROL Assistant Requête : Étape 1]. L’ajout de plusieurs dimensions à l’étape 2 permet de créer une répartition dans votre requête de données.

   Voir [Ajouter des mesures et des dimensions](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) pour plus d’informations.
