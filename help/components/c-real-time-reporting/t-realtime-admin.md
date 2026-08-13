---
description: Cette rubrique décrit les étapes d’administration pour configurer les rapports en temps réel.
title: Configuration de rapports en temps réel
feature: Real-time
exl-id: 9e7fc67c-71d5-465a-9553-5bb7e02a9bfd
TQID: https://experienceleague.adobe.com/wmZj-F8P4ectiMUnpy9yYT-pviys2m2aBGAVtP5kNNI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 288
ht-degree: 74%

---

# Configuration de rapports en temps réel

Les informations suivantes contiennent les étapes administratives pour configurer des rapports en temps réel.

Elle consiste à sélectionner la suite de rapports et à configurer jusqu’à 3 rapports pour celle-ci.

1. Sélectionnez la suite de rapports pour laquelle activer les rapports en temps réel.

   1. Dans Analysis Workspace, sélectionnez l&#39;onglet [!UICONTROL **Workspace**], puis sélectionnez [!UICONTROL **Rapports**] > [!UICONTROL **Engagement**] > **[!UICONTROL Temps réel]**.

   1. Sélectionnez la suite de rapports dans le menu déroulant du haut :

      ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/report_suite_selector.png)

      Si vous essayez d’afficher des rapports en temps réel pour une suite de rapports qui n’a pas été configurée pour la création de rapports en temps réel, un message s’affiche. Celui-ci vous permet de configurer la suite de rapports.

      ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/rep_suite_not_set_up.png)

1. Sélectionnez **[!UICONTROL Configurer]** pour exécuter le [!UICONTROL Gestionnaire de suites de rapports].

   (Également disponible sous **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Temps réel]**.)

1. Activez le paramètre **[!UICONTROL Activer le temps réel]**.
1. Configurez la collecte de données en temps réel pour trois rapports au maximum, avec une mesure et trois dimensions ou classifications par rapport.

   ![](assets/real_time_admin.png)

   Pour plus d’informations sur les mesures et dimensions en temps réel prises en charge, voir [Mesures et dimensions prises en charge](/help/admin/tools/manage-rs/edit-settings/realtime/realtime-metrics.md).

   Si vous avez créé des classifications, elles apparaissent en retrait sous la dimension pour laquelle elles ont été définies :

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >Pour un rapport Temps réel unique, les dimensions en double ne sont pour l’instant pas prises en charge, même si une autre classification est sélectionnée pour chaque dimension.

   >[!NOTE]
   >
   >Certaines dimensions (telles que « Mot-clé de recherche » ou « Produit ») ne persistent pas dans le rapport Temps réel comme elles le font ailleurs dans Adobe Analytics. Lorsque vous sélectionnez une mesure non permanente, cet avertissement s’affiche :

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/warning_dimensions.png)

1. Sélectionnez **[!UICONTROL Enregistrer]** ou **[!UICONTROL Enregistrer et afficher le rapport]**.

   Après cette configuration initiale du rapport, comptez jusqu’à 20 minutes pour que les données commencent à se diffuser. À partir de là, les données sont immédiatement disponibles.

1. Par défaut, tous les utilisateurs ont accès aux rapports Temps réel.
