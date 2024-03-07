---
description: Découvrez comment activer le compte rendu des performances Adobe Campaign Standard dans Adobe Analytics
title: Comment intégrer le compte rendu des performances Adobe Campaign Standard dans Adobe Analytics ?
feature: Campaign Integration
exl-id: 63bae5ee-f94d-43fa-87ce-6380236745d6
role: Admin
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 99%

---


# Compte rendu des performances Adobe Campaign Standard

Pour plus d’informations sur la configuration de cette intégration, aller à la [documentation d’Adobe Campaign](https://helpx.adobe.com/fr/campaign/standard/integrating/using/about-campaign-analytics-integration.html).

>[!IMPORTANT]
>Cet article s’applique au compte rendu des performances Adobe Campaign **Standard** uniquement. Voir [ici](https://experienceleague.adobe.com/docs/analytics/integration/analytics-to-campaign-classic.html) pour ajouter le compte rendu des performances Adobe Campaign **Classic**.

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

* **[!UICONTROL ID de diffusion exécutée Adobe Campaign]** : affiche les données importées depuis Adobe Campaign relatives à des e-mails envoyés depuis Adobe Campaign.

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
| Libellé de la diffusion exécutée | Identifiants des diffusions exécutées uniquement. Aucun identifiant de diffusion maître récurrente/de transactions. Exemple : une diffusion récurrente DM1 était planifiée et DM2, DM3, DM4 et DM5 étaient des diffusions enfants de la diffusion récurrente. L’identifiant Diffusion exécutée affiche les résultats pour toutes les diffusions, de DM2 à DM5, c’est-à-dire les diffusions qui ont été effectivement exécutées. |
| Libellé de la diffusion exécutée | Libellés des identifiants Diffusion exécutée |
