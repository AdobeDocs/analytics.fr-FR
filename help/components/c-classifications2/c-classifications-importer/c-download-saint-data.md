---
description: (Facultatif) Avant d’importer des classifications dans des rapports marketing, vous pouvez télécharger un modèle qui vous aide à créer un fichier de données de classification. Le fichier de données utilise les classifications de votre choix comme en-têtes de colonne, puis classe le jeu de données  sous les en-têtes de classification appropriés.
subtopic: Classifications
title: Modèle de classification
topic: Admin tools
uuid: 4edd411b-164c-4b4d-a872-b57a3163ca72
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Modèle de classification

(Facultatif) Avant d’importer des classifications dans des rapports marketing, vous pouvez télécharger un modèle qui vous aide à créer un fichier de données de classification. Le fichier de données utilise les classifications de votre choix comme en-têtes de colonne, puis classe le jeu de données  sous les en-têtes de classification appropriés.

## Modèle de classification {#concept_0F06847AD8D042F5BA818AE3C37E2417}

(Facultatif) Avant d’importer des classifications dans des rapports marketing, vous pouvez télécharger un modèle qui vous aide à créer un fichier de données de classification. Le fichier de données utilise les classifications de votre choix comme en-têtes de colonne, puis classe le jeu de données  sous les en-têtes de classification appropriés.

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

| Elément | Description |
|---|---|
| Sélectionner une suite de rapports | Sélectionnez la suite de rapports à utiliser dans le modèle. La suite de rapports et l’ensemble de données doivent correspondre. |
| Données à classer | Sélectionnez le type de données pour le fichier de données. Le menu inclut tous les rapports de vos suites de rapports qui sont configurés pour les classifications. |
| Exporter Numérique 2 | Vous pouvez importer des classifications numériques 2 dans le système par l’intermédiaire de l’importateur. Les classifications numériques 2 sont utiles pour les variables qui changent au fil du temps pour différents éléments, comme les valeurs de coût et de budget pour le [!UICONTROL Marketing Channel] rapport. Voir [Classifications numériques 2](/help/components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md) pour plus d’informations sur le chargement de données utilisant les classifications numériques 2. |
| Codage  | Sélectionnez le codage des caractères pour le fichier de données. Le format de codage par défaut est UTF-8. |
| Télécharger | Télécharge le fichier de modèle. |

Le modèle inclut les classifications actuellement définies (en-têtes de colonne) d’un jeu de données spécifique sans inclure les données associées à chaque classification.

>[!NOTE] La méthode Modèle limite le téléchargement des données de classification à une seule suite de rapports.

Pour plus d’informations sur la structure d’un fichier de données, consultez la section [À propos des fichiers de données de classification](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md).

## Télécharger un modèle de données de classification (facultatif) {#task_8DFCF309B6FD43ABB1D6FEE9AFAEC596}

Le modèle fournit le format de fichier que vous devez respecter pour les classifications.

>[!NOTE] La méthode Modèle limite le téléchargement des données à une seule suite de rapports.

1. Cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. On the **[!UICONTROL Download Template]** tab, specify the [data template configuration](/help/components/c-classifications2/c-classifications-importer/c-download-saint-data.md).
1. Cliquez sur **[!UICONTROL Download]**.
1. Enregistrez le fichier de modèle sur votre système local.

   Le fichier de modèle est un fichier de données délimité par des tabulations (extension de nom de fichier [!DNL .tab] ) qui est pris en charge par la plupart des tableurs.

