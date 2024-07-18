---
description: Décrit les étapes d’application de filtres à un rapport sur les abandons.
title: Filtrage d’un rapport sur les abandons à l’aide de l’Assistant Requête
feature: Report Builder
role: User, Admin
exl-id: 6134d7d4-7287-4a83-92b6-d250ca15cf69
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 91%

---

# Filtrage d’un rapport sur les abandons à l’aide de l’Assistant Requête

Décrit les étapes d’application de filtres à un rapport sur les abandons.

Cet exemple affiche le rapport Page - Abandon.

1. Dans le Report Builder d’Adobe, cliquez sur **[!UICONTROL Créer]** pour ouvrir l’Assistant Requête.
1. Sélectionnez la suite de rapports appropriée.
1. Dans l’arborescence de gauche, sélectionnez **[!UICONTROL Chemins]** > **[!UICONTROL Page]** > **[!UICONTROL Page - Abandon]**.

   ![Capture d’écran présentant l’arborescence Windows du répertoire de Report Builder. L’option Page Fallout est sélectionnée.](assets/page_fallout.png)

1. Configurez les [périodes](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) appropriées.
1. Cliquez sur **[!UICONTROL Suivant]**.
1. À l’étape 2 de l’Assistant, sous **[!UICONTROL Libellés de lignes]**, cliquez sur le lien **[!UICONTROL Définir les points de contrôle]**. (Dans un rapport d’abandon, vous devez toujours définir des éléments de chemin, à la différence d’un rapport de cheminement où un modèle est pré-appliqué.)

   ![Capture d&#39;écran montrant le lien Définir les points de contrôle.](assets/define_checkpoints.png)

1. Sélectionnez l’option **[!UICONTROL Filtrer]**.

1. Dans la boîte de dialogue **[!UICONTROL Définir des points de contrôle d’abandon de section de site]**, définissez les points de contrôle depuis une plage de cellules ou depuis une liste. Puis, cliquez sur **[!UICONTROL OK]**.
1. Choisissez d’effectuer la sélection depuis une plage de cellules ou depuis une liste.
1. Si vous sélectionnez depuis une liste, cliquez sur **[!UICONTROL Ajouter]** pour sélectionner des points de contrôle à ajouter au chemin d’abandon. Vous pouvez définir entre 3 et 8 points de contrôle. (Recherchez des éléments disponibles en cliquant sur **[!UICONTROL Plus]**.)

   Pour plus d’informations sur l’affinage du filtre, voir [Filtres de dimension](/help/analyze/report-builder/layout/c-filter-dimensions/filter-dimensions.md). 1. Déplacez les **[!UICONTROL éléments disponibles]** de la colonne de gauche à celle de droite en les sélectionnant et en cliquant sur la flèche orange.
1. Cliquez à trois reprises sur **[!UICONTROL OK]**, puis cliquez sur **[!UICONTROL Terminer]**.

   Le rapport devrait à présent s’actualiser.
