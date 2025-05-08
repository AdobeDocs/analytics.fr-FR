---
description: Cette rubrique décrit les étapes d’administration pour configurer les rapports en temps réel.
title: Configuration des rapports en temps réel
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 76%

---

# Configuration des rapports en temps réel

Cette rubrique décrit les étapes d’administration pour configurer les rapports en temps réel.

La configuration des rapports en temps réel dans Adobe Analytics consiste à sélectionner la suite de rapports et à configurer jusqu’à 3 rapports pour celle-ci. Par défaut, tous les utilisateurs ont accès aux rapports Temps réel.

1. Sélectionnez la suite de rapports pour laquelle activer les rapports en temps réel.

   Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Suites de rapports]**.

1. Cliquez sur **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Temps réel]**.

1. Configurez la collecte de données en temps réel pour trois rapports au maximum, avec une mesure et trois dimensions ou classifications par rapport.

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/real_time_admin.png)

   Pour plus d’informations sur les mesures et dimensions en temps réel prises en charge, voir [Mesures et dimensions prises en charge](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md).

   Si vous avez créé des classifications, elles apparaissent en retrait sous la dimension pour laquelle elles ont été définies :

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >Pour un rapport Temps réel unique, les dimensions en double ne sont pour l’instant pas prises en charge, même si une autre classification est sélectionnée pour chaque dimension.

   >[!NOTE]
   >
   >Certaines dimensions (telles que « Mot-clé de recherche » ou « Produit ») ne persistent pas dans le rapport Temps réel comme elles le font ailleurs dans Adobe Analytics. Lorsque vous sélectionnez une mesure non permanente, cet avertissement s’affiche :

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/warning_dimensions.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

   Après cette configuration initiale du rapport, comptez jusqu’à 20 minutes pour que les données commencent à se diffuser. À partir de là, les données sont immédiatement disponibles.

1. Pour afficher le rapport en temps réel, accédez à :

   **[!UICONTROL Workspace]** > **[!UICONTROL Rapports]** > **[!UICONTROL Engagement]** > **[!UICONTROL Temps réel]**.

