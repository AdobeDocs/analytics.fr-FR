---
description: Découvrez comment créer une requête de détection des anomalies dans Report Builder.
title: Configuration d’une requête de détection des anomalies
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 72%

---

# Configuration d’une requête de détection des anomalies

{{legacy-arb}}

Pour créer une requête de détection des anomalies dans Report Builder :

1. Sélectionnez un rapport de tendance, par exemple sur un rapport **[!UICONTROL Mesures du site]** > **[!UICONTROL Trafic]**.
1. Dans le menu [!UICONTROL Appliquer la granularité], sélectionnez **[!UICONTROL Jour]**.

   >[!NOTE]
   >
   >Le menu [!UICONTROL Détection des anomalies] n’est disponible que lorsque vous sélectionnez la granularité Jour. Les 30 jours précédents de données sont utilisés comme période de formation des données statistiques, quelle que soit la plage de données que vous sélectionnez.

1. Après avoir configuré les plages de données, cliquez sur **[!UICONTROL Suivant]**.

   Dans l’Assistant Requête : Étape 2 sur 2, ajoutez une mesure, par exemple **[!UICONTROL Visites]**.

   Pour la mesure ajoutée, cliquez sur le lien **[!UICONTROL Aucun]**.

   ![Capture d&#39;écran montrant la détection des anomalies, puis Insérer et insérer des options pour la limite inférieure et supérieure et attendue.](assets/anomaly_select.png)

1. Sélectionnez **[!UICONTROL Détection des anomalies]** > **[!UICONTROL `<selection>`]**.

   ![Capture d’écran montrant l’Assistant Requête : Étape 2 - Rapport de trafic.](assets/anomaly_visit.png)

   Lorsque vous sélectionnez l’une de ces options, le système crée des copies Détection des anomalies de la mesure d’origine. Par exemple, pour la mesure Visite, une mesure Limite inférieure - Visite est ajoutée au groupe [!UICONTROL Mesure].
1. Cliquez sur **[!UICONTROL Terminer]** et sélectionnez la cellule pour la sortie vers Excel.

   Reportez-vous à la section [Détection des anomalies](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) pour les définitions.
