---
description: Étapes qui décrivent comment configurer les dates de requête en temps réel.
title: Configuration d’une requête en temps réel
feature: Report Builder
role: User, Admin
exl-id: 818fc9ca-aa78-4a21-abd7-8e3144f5d1c0
TQID: https://experienceleague.adobe.com/qXZLxRetXZPviC02dJfP58Q9EXRjo0gXA-8EEJt5p4U
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 120
ht-degree: 48%

---

# Configuration d’une requête en temps réel

{{legacy-arb}}

Pour configurer les dates de requête en temps réel :

1. Assurez-vous que la création de rapports en temps réel est activée dans les [&#x200B; Outils d’administration &#x200B;](/help/admin/tools/manage-rs/edit-settings/realtime/t-realtime-admin.md).
1. Dans l’[!UICONTROL Assistant Requête : Étape 1], cliquez sur **[!UICONTROL Rapport en temps réel]** > **[!UICONTROL `<report type>`]**

   Par exemple, sélectionnez un rapport de trafic. Lorsque vous sélectionnez un type de rapport en temps réel, les options [!UICONTROL Sélectionner une période] s’affichent.

1. Sélectionnez une plage de temps en minutes ou heures.

   ![Capture d’écran affichant les options Sélectionner une plage horaire avec les 60 dernières minutes sélectionnées.](assets/real_time_select_date.png)

   Les rapports en temps réel ne sont disponibles que pour les 20 dernières heures. Pour la granularité, vous avez la possibilité de sélectionner une granularité comprise entre 1 minute et 30 minutes.
1. Cliquez sur **[!UICONTROL Suivant]** et continuez à [configurer la disposition de la requête](/help/analyze/legacy-report-builder/layout/layout.md).
