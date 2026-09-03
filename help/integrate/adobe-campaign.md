---
description: Découvrez comment activer le compte rendu des performances Adobe Campaign Standard dans Adobe Analytics
title: Comment intégrer le compte rendu des performances Adobe Campaign Standard dans Adobe Analytics ?
feature: Admin Tools
exl-id: 63bae5ee-f94d-43fa-87ce-6380236745d6
role: Admin
autotag-review: '2026-05-22T12:17:50.968Z'
TQID: 'https://experienceleague.adobe.com/r-zrWBcHhMkxptxKlfZ0Xaw-UsYc9QIIqQgSbyTertA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: b13acd70-7a51-4028-8c44-5f3b1bbe3ad4
  - id: fe0a7292-80bc-407a-b456-64170267d1cc
  - id: a9364d69-0c51-44bf-8b5f-6d99c04493b8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 520
ht-degree: 96%

---

# Compte rendu des performances Adobe Campaign Standard

Pour plus d’informations sur la configuration de cette intégration, aller à la [documentation d’Adobe Campaign](https://helpx.adobe.com/fr/campaign/standard/integrating/using/about-campaign-analytics-integration.html).

>[!IMPORTANT]
>Cet article s’applique au compte rendu des performances Adobe Campaign **Standard** uniquement. Voir [ici](/help/integrate/analytics-to-campaign-classic.md) pour ajouter le compte rendu des performances Adobe Campaign **Classic**.

Cette intégration entre Adobe Analytics et Adobe Campaign Standard :

* permet de partager vos données IPC (Indicateur de performance clé) provenant d’Adobe Campaign Standard avec Adobe Analytics ;
* enrichit les formules de suivi avec les paramètres d’Adobe Analytics ;
* ajoute un nouveau rapport sous **[!UICONTROL Analytics]** > **[!UICONTROL Rapports]** > **[!UICONTROL Adobe Campaign.]**
* ajoute 5 nouvelles classifications Adobe Campaign ;
* ajoute 9 nouvelles mesures Adobe Campaign ;
* ajoute 6 nouvelles dimensions Adobe Campaign ;
* synchronise les données avec Analytics toutes les 15 minutes par le biais d’une source de données automatiquement configurée.

## Étape 1. Activer le compte rendu des performances Adobe Campaign Standard {#section_C685EF10505045708A6536BB13F6CD58}

Pour afficher les données de Campaign Standard dans Analytics, vous devez d’abord activer le compte rendu des performances dans le gestionnaire de suites de rapports.

1. Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **`<select report suite>`** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Rapports Adobe Campaign]** .
1. Cliquez sur **[!UICONTROL Activer les rapports Adobe Campaign]**.

   ![](assets/enable-campaign.png)

## Étape 2. Afficher les rapports Adobe Campaign {#section_9C18A29F3CC54BD4AC5EA96417F17B33}

L’intégration entre Adobe Campaign Standard et Adobe Analytics ajoute le rapport suivant sous **[!UICONTROL Analytics]** > **[!UICONTROL Rapports]**.

* **[!UICONTROL Adobe Campaign Executed Delivery ID]** : affiche les données importées depuis Adobe Campaign à propos des emails envoyés depuis Adobe Campaign. |

## Étape 3. Utiliser les classifications Adobe Campaign {#section_74A28AF3F4CA4091943789DE4D8B2B63}

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **`<select report suite>`** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Classifications Adobe Campaign]**

Une fois votre suite de rapports activée pour Adobe Campaign, les classifications suivantes sont disponibles :

| Classification | Description |
| --- | --- |
| [!UICONTROL ID de diffusion] | Nom de la diffusion interne s’affichant dans Campaign |
| [!UICONTROL Libellé de diffusion] | Diffusion dans Campaign : diffusion individuelle/diffusion récurrente/diffusion de transactions |
| [!UICONTROL ID de campagne] | Nom de la campagne interne s’affichant dans Campaign |
| [!UICONTROL Libellé de campagne] | Campagne dans Adobe Campaign |
| [!UICONTROL Libellé de diffusion exécutée] | Liste des diffusions individuelles exécutées |

## Dimensions et mesures Adobe Campaign Standard disponibles dans Adobe Analytics {#section_F33385C9660644AF84172EC39601469B}

Les **mesures** suivantes sont disponibles depuis Campaign dans les suites de rapports d’Adobe Analytics :

* Adobe Campaign Envoyés
* Adobe Campaign Ouverts
* Adobe Campaign Cliqués
* Adobe Campaign Délivrés
* Adobe Campaign Ouvertures uniques
* Clics uniques Adobe Campaign
* Adobe Campaign Désinscriptions
* Adobe Campaign Bounces total
* Adobe Campaign Instances Identifiant Diffusion exécutée

Les **dimensions** suivantes sont disponibles depuis Campaign dans les suites de rapports d’Adobe Analytics :

| Nom de la dimension | Définition |
| --- | --- |
| ID de campagne | ID de toutes les campagnes pour lesquelles des IPC ont été envoyés pendant la durée. |
| Libellé de la campagne | Libellés des ID de campagne |
| Identifiant de la diffusion | Identifiant de toutes les diffusions pour lesquelles des IPC ont été envoyés pendant la durée. Inclut également les identifiants des diffusions maîtres de la diffusion récurrente et de la diffusion des transactions. Exemple : une diffusion récurrente DM1 était planifiée et DM2, DM3, DM4 et DM5 étaient des diffusions enfants de la diffusion récurrente.  L’identifiant de la diffusion affiche les résultats pour toutes les diffusions, de DM1 à DM5. |
| Libellé de diffusion | Libellés des identifiants de diffusion |
| Libellé de la diffusion exécutée | Identifiants des diffusions exécutées uniquement. Aucun identifiant de diffusion principale récurrente/transactionnelle. Exemple : une diffusion récurrente DM1 était planifiée et DM2, DM3, DM4 et DM5 étaient des diffusions enfants de la diffusion récurrente. L’identifiant Diffusion exécutée affiche les résultats pour toutes les diffusions, de DM2 à DM5, c’est-à-dire les diffusions qui ont été effectivement exécutées. |
| Libellé de la diffusion exécutée | Libellés des identifiants Diffusion exécutée |
