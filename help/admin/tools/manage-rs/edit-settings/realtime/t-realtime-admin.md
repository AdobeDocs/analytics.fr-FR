---
description: Cette rubrique décrit les étapes d’administration pour configurer les rapports en temps réel.
title: Configuration des rapports en temps réel
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
TQID: https://experienceleague.adobe.com/HTu1UvUUIGK0SzAQWEFBclV-P1JaPCJUp6j5MiYC3A0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 226
ht-degree: 76%

---

# Configuration des rapports en temps réel

Cette rubrique décrit les étapes d’administration pour configurer les rapports en temps réel.

La configuration des rapports en temps réel dans Adobe Analytics consiste à sélectionner la suite de rapports et à configurer jusqu’à 3 rapports pour celle-ci. Par défaut, tous les utilisateurs ont accès aux rapports Temps réel.

1. Sélectionnez la suite de rapports pour laquelle activer les rapports en temps réel.

   Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Suites de rapports]**.

1. Cliquez sur **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Temps réel]**.

1. Configurez la collecte de données en temps réel pour trois rapports au maximum, avec une mesure et trois dimensions ou classifications par rapport.

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/real_time_admin.png)

   Pour plus d’informations sur les mesures et dimensions en temps réel prises en charge, voir [Mesures et dimensions prises en charge](/help/admin/tools/manage-rs/edit-settings/realtime/realtime-metrics.md).

   Si vous avez créé des classifications, elles apparaissent en retrait sous la dimension pour laquelle elles ont été définies :

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >Pour un rapport Temps réel unique, les dimensions en double ne sont pour l’instant pas prises en charge, même si une autre classification est sélectionnée pour chaque dimension.

   >[!NOTE]
   >
   >Certaines dimensions (telles que « Mot-clé de recherche » ou « Produit ») ne persistent pas dans le rapport Temps réel comme elles le font ailleurs dans Adobe Analytics. Lorsque vous sélectionnez une mesure non permanente, cet avertissement s’affiche :

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/warning_dimensions.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

   Après cette configuration initiale du rapport, comptez jusqu’à 20 minutes pour que les données commencent à se diffuser. À partir de là, les données sont immédiatement disponibles.

1. Pour afficher le rapport en temps réel, accédez à :

   **&#x200B;**&#x200B;> **[!UICONTROL Rapports]** > **[!UICONTROL Engagement]** > **[!UICONTROL Temps réel]**.

