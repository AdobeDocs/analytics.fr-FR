---
description: Étapes qui décrivent comment créer une requête de détection des anomalies dans le créateur de rapports.
title: Configuration d’une requête de détection des anomalies
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 98%

---


# Configuration d’une requête de détection des anomalies

Étapes qui décrivent comment créer une requête de détection des anomalies dans le créateur de rapports.

1. Sélectionnez un rapport de tendance, par exemple sur un rapport **[!UICONTROL Mesures du site]** > **[!UICONTROL Trafic]**.
1. Dans le menu [!UICONTROL Appliquer la granularité], sélectionnez **[!UICONTROL Jour]**.

   >[!NOTE]
   >
   >Le menu [!UICONTROL Détection des anomalies] n’est disponible que lorsque vous sélectionnez la granularité Jour. Les 30 jours précédents de données sont utilisés comme période de formation des données statistiques, quelle que soit la plage de données que vous sélectionnez.

1. Après avoir configuré les plages de données, cliquez sur **[!UICONTROL Suivant]**.

   Résultat de l’étape 1. Dans l’Assistant Requête : Étape 2 sur 2, ajoutez une mesure, par exemple **[!UICONTROL Visites]**.

   Résultat de l’étape 1. Pour la mesure ajoutée, cliquez sur le lien **[!UICONTROL Aucun]**.

   ![Résultat de l’étape](assets/anomaly_select.png)

1. Sélectionnez **[!UICONTROL Détection des anomalies]** > **[!UICONTROL `<selection>`]**.

   ![Infos sur l’étape](assets/anomaly_visit.png)

   Lorsque vous sélectionnez l’une de ces options, le système crée des copies Détection des anomalies de la mesure d’origine. Par exemple, pour la mesure Visite, une mesure Limite inférieure - Visite est ajoutée au groupe [!UICONTROL Mesure].
1. Cliquez sur **[!UICONTROL Terminer]** et sélectionnez la cellule pour la sortie vers Excel.

   Reportez-vous à la section [Détection des anomalies](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) pour les définitions.
