---
description: Cette rubrique décrit les étapes d’administration pour configurer les rapports en temps réel.
title: Configuration de rapports en temps réel
feature: Real-time
exl-id: 9e7fc67c-71d5-465a-9553-5bb7e02a9bfd
source-git-commit: ee55349a8c676023a5ce33b56592cad7642199b8
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 78%

---

# Configuration de rapports en temps réel

Les informations suivantes contiennent les étapes administratives permettant de configurer des rapports en temps réel.

Cela consiste à sélectionner la suite de rapports et à configurer jusqu’à trois rapports pour celle-ci.

1. Sélectionnez la suite de rapports pour laquelle activer les rapports en temps réel.

   1. Dans Analysis Workspace, sélectionnez l’onglet [!UICONTROL **Workspace**], puis sélectionnez [!UICONTROL **Rapports**] > [!UICONTROL **Engagement**] > **[!UICONTROL Temps réel]**.

   1. Sélectionnez la suite de rapports dans la liste déroulante supérieure :

      ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/report_suite_selector.png)

      Si vous essayez d’afficher des rapports en temps réel pour une suite de rapports qui n’a pas été configurée pour la création de rapports en temps réel, un message s’affiche. Celui-ci vous permet de configurer la suite de rapports.

      ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/rep_suite_not_set_up.png)

1. Sélectionnez **[!UICONTROL Configurer]** pour exécuter le [!UICONTROL Gestionnaire de Report Suites].

   (Également disponible sous **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Temps réel]**.)

1. Activez le paramètre **[!UICONTROL Activer le temps réel]**.
1. Configurez la collecte de données en temps réel pour trois rapports au maximum, avec une mesure et trois dimensions ou classifications par rapport.

   ![](assets/real_time_admin.png)

   Pour plus d’informations sur les mesures et dimensions en temps réel prises en charge, voir [Mesures et dimensions prises en charge](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md).

   Si vous avez créé des classifications, elles apparaissent en retrait sous la dimension pour laquelle elles ont été définies :

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >Pour un rapport Temps réel unique, les dimensions en double ne sont pour l’instant pas prises en charge, même si une autre classification est sélectionnée pour chaque dimension.

   Pour plus d’informations sur les classifications, voir [À propos des classifications](/help/components/classifications/c-classifications.md).

   >[!NOTE]
   >
   >Certaines dimensions (telles que « Mot-clé de recherche » ou « Produit ») ne persistent pas dans le rapport Temps réel comme elles le font ailleurs dans Adobe Analytics. Lorsque vous sélectionnez une mesure non permanente, cet avertissement s’affiche :

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/warning_dimensions.png)

1. Sélectionnez **[!UICONTROL Enregistrer]** ou **[!UICONTROL Enregistrer et afficher le rapport]**.

   Après cette configuration initiale du rapport, comptez jusqu’à 20 minutes pour que les données commencent à se diffuser. À partir de ce moment, les données sont immédiatement disponibles. Pour en savoir plus sur l’affichage des rapports Temps réel, voir [Exécution d’un rapport Temps réel](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/t-running-report-types.html?lang=fr).

1. Par défaut, tous les utilisateurs ont accès aux rapports Temps réel.
