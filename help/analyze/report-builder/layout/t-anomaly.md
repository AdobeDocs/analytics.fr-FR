---
description: Étapes qui décrivent comment créer une requête de détection des anomalies dans le Créateur de rapports.
seo-description: Etapes qui décrivent comment créer une requête de détection des anomalies dans le créateur de rapports.
seo-title: Configurer une requête de détection des anomalies
solution: Analytics
title: Configuration d’une requête de détection des anomalies
topic: Créateur de rapports
uuid: 1 e 504 ff 9-df 88-4 fa 7-95 ea -1 ca 05 a 6 f 9 c 0 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Configuration d’une requête de détection des anomalies

Étapes qui décrivent comment créer une requête de détection des anomalies dans le Créateur de rapports.

1. Sélectionnez un rapport de tendance, par exemple sur un rapport **Mesures du site** &gt; **[!UICONTROL Trafic.]**
1. Dans le menu [!UICONTROL Appliquer la granularité]**, sélectionnez[!UICONTROL Jour]**.

   >[!NOTE]
   >
   >The [!UICONTROL Anomaly Detection] menu is available only when you select Day granularity. Les 30 jours précédents de données sont utilisés comme période de formation des données statistiques, quelle que soit la plage de données que vous sélectionnez.

1. After configuring date ranges, click **[!UICONTROL Next]**.

   Résultat 1. On the Request Wizard: Step 2 of 2, add a metric, such as **[!UICONTROL Visits]**.

   Résultat 1. For the added metric, click the **[!UICONTROL None]** link.

   ![Résultat de l’étape](assets/anomaly_select.png)

1. Select **[!UICONTROL Anomaly Detection]** &gt; **[!UICONTROL `<selection>`]**.

   ![Informations sur les étapes](assets/anomaly_visit.png)

   Lorsque vous sélectionnez l’une de ces options, le système crée des copies Détection des anomalies de la mesure d’origine. Par exemple, pour la mesure Visite, une mesure Limite inférieure - Visite est ajoutée au groupe [!UICONTROL Mesure].
1. Click **[!UICONTROL Finish]** and select the cell for output to Excel.

   See [Anomaly Detection](../../../analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md#concept_9476D6C093334B1A8044AE63835BDBE7) for definitions.
