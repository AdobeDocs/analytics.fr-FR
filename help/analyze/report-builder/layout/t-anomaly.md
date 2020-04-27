---
description: Étapes qui décrivent comment créer une requête de détection des anomalies dans le créateur de rapports.
title: Configuration d’une requête de détection des anomalies
topic: Report builder
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Configuration d’une requête de détection des anomalies

Étapes qui décrivent comment créer une requête de détection des anomalies dans le créateur de rapports.

1. Sélectionnez un rapport de tendances, tel qu’un rapport **[!UICONTROL Site Metrics]** > **[!UICONTROL Traffic]** .
1. Dans le [!UICONTROL Apply Granularity] menu, sélectionnez **[!UICONTROL Day]**.

   >[!NOTE]
   >
   >The [!UICONTROL Anomaly Detection] menu is available only when you select Day granularity. Les 30 jours précédents de données sont utilisés comme période de formation des données statistiques, quelle que soit la plage de données que vous sélectionnez.

1. After configuring date ranges, click **[!UICONTROL Next]**.

   Résultat de l’étape 1. On the Request Wizard: Step 2 of 2, add a metric, such as **[!UICONTROL Visits]**.

   Résultat de l’étape 1. For the added metric, click the **[!UICONTROL None]** link.

   ![Résultat de l’étape](assets/anomaly_select.png)

1. Sélectionner **[!UICONTROL Anomaly Detection]** > **[!UICONTROL `<selection>`]**.

   ![Infos sur l’étape](assets/anomaly_visit.png)

   Lorsque vous sélectionnez l’une de ces options, le système crée des copies Détection des anomalies de la mesure d’origine. For example, for the Visit metric, a Lower Bound Visit metric is added to the [!UICONTROL Metric] group.
1. Click **[!UICONTROL Finish]** and select the cell for output to Excel.

   Reportez-vous à la section [Détection des anomalies](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) pour les définitions.
