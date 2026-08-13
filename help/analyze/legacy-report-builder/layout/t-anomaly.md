---
description: Découvrez comment créer une requête de détection des anomalies dans Report Builder.
title: Configuration d’une requête de détection des anomalies
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
TQID: https://experienceleague.adobe.com/9qyfB3mtj7QKDNLL1PRrQ2-3lzrb19-7gL4rnfxbph4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: c67272a6-888e-425e-9e97-a87304637eed
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 54%

---

# Configuration d’une requête de détection des anomalies

{{legacy-arb}}

Création d’une requête de détection des anomalies dans Report Builder :

1. Sélectionnez un rapport de tendance, par exemple sur un rapport **[!UICONTROL Mesures du site]** > **[!UICONTROL Trafic]**.
1. Dans le menu [!UICONTROL Appliquer la granularité], sélectionnez **[!UICONTROL Jour]**.

   >[!NOTE]
   >
   >Le menu [!UICONTROL Détection des anomalies] n’est disponible que lorsque vous sélectionnez la granularité Jour. Les 30 jours précédents de données sont utilisés comme période de formation des données statistiques, quelle que soit la plage de données que vous sélectionnez.

1. Après avoir configuré les plages de données, cliquez sur **[!UICONTROL Suivant]**.

   Dans l’Assistant Requête : Étape 2 sur 2, ajoutez une mesure, par exemple **[!UICONTROL Visites]**.

   Pour la mesure ajoutée, cliquez sur le lien **[!UICONTROL Aucun]**.

   ![Capture d’écran affichant la détection des anomalies, puis les options Insérer et Insérer pour les limites inférieure et supérieure et attendue.](assets/anomaly_select.png)

1. Sélectionnez **[!UICONTROL Détection des anomalies]** > **[!UICONTROL `<selection>`]**.

   ![Capture d’écran affichant l’étape 2 de l’assistant Requête - Rapport de trafic.](assets/anomaly_visit.png)

   Lorsque vous sélectionnez l’une de ces options, le système crée des copies de détection des anomalies de la mesure d’origine. Par exemple, pour la mesure Visite , une mesure Visite limite inférieure est ajoutée au groupe [!UICONTROL Mesure].
1. Cliquez sur **[!UICONTROL Terminer]** et sélectionnez la cellule pour la sortie vers Excel.

   Reportez-vous à la section [Détection des anomalies](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) pour les définitions.
