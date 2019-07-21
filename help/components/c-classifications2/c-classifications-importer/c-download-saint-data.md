---
description: (Facultatif) Avant d’importer des classifications dans des rapports marketing, vous pouvez télécharger un modèle qui vous aide à créer un fichier de données de classification. Ce fichier de données utilise les classifications voulues sous la forme d’en-têtes de colonne, puis classe le jeu de données de rapport sous les en-têtes de classification adéquats.
seo-description: (Facultatif) Avant d’importer des classifications dans des rapports marketing, vous pouvez télécharger un modèle qui vous aide à créer un fichier de données de classification. Ce fichier de données utilise les classifications voulues sous la forme d’en-têtes de colonne, puis classe le jeu de données de rapport sous les en-têtes de classification adéquats.
seo-title: Modèle de classification
solution: Analytics
subtopic: Gestionnaire
title: Modèle de classification
topic: Outils d’administration
uuid: 4 edd 411 b -164 c -4 b 4 d-a 872-b 57 a 3163 ca 72
translation-type: tm+mt
source-git-commit: 1986561a83f22619b627d754376f7e936902a737

---


# Modèle de classification

(Facultatif) Avant d’importer des classifications dans des rapports marketing, vous pouvez télécharger un modèle qui vous aide à créer un fichier de données de classification. Ce fichier de données utilise les classifications voulues sous la forme d’en-têtes de colonne, puis classe le jeu de données de rapport sous les en-têtes de classification adéquats.

## Classification template {#concept_0F06847AD8D042F5BA818AE3C37E2417}

(Facultatif) Avant d’importer des classifications dans des rapports marketing, vous pouvez télécharger un modèle qui vous aide à créer un fichier de données de classification. Ce fichier de données utilise les classifications voulues sous la forme d’en-têtes de colonne, puis classe le jeu de données de rapport sous les en-têtes de classification adéquats.

**[!UICONTROL Admin]** &gt; **[!UICONTROL Importateur de classifications]**.

| Élément | Description |
|---|---|
| Sélectionner une Report Suite | Sélectionnez la suite de rapports à utiliser dans le modèle. La suite de rapports et l’ensemble de données doivent correspondre. |
| Données à classer | Sélectionnez le type de données pour le fichier de données. Le menu comprend tous les rapports des suites de rapports qui sont configurés pour les classifications. |
| Exporter Numérique 2 | Vous pouvez importer les classifications numériques 2 dans le système à l’aide de l’importateur. Les classifications numériques 2 s’avèrent utiles lorsque les variables de différents articles changent de temps à autre, comme les valeurs de coût et de budget pour le rapport [!UICONTROL Canal marketing]. See [Numeric 2 Classifications](../../../components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md#concept_71024B7B91DF4E909076062AB1380D8B) for information about uploading data using numeric 2 classifications. |
| Encodage | Sélectionnez le codage des caractères pour le fichier de données. Le format de codage par défaut est UTF-8. |
| Téléchargement | Télécharge le fichier de modèle. |

Ce modèle comprend les classifications actuellement définies (en-têtes de colonne) pour un ensemble de données spécifiques sans inclure les données associées à chaque classification.

>[!NOTE]
>
>La méthode Modèle limite le téléchargement des données de classification à une seule suite de rapports.

For more information about the data file structure, see [About Classification Data Files](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_EBA7669C546040BE8162ADACA3548735).

## Télécharger un modèle de données de classification (facultatif) {#task_8DFCF309B6FD43ABB1D6FEE9AFAEC596}

Le modèle fournit le format de fichier que vous devez respecter pour les classifications.

>[!NOTE]
>
>La méthode Modèle limite le téléchargement de données à une seule suite de rapports.

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. On the **[!UICONTROL Download Template]** tab, specify the [data template configuration](../../../components/c-classifications2/c-classifications-importer/c-download-saint-data.md#concept_0F06847AD8D042F5BA818AE3C37E2417).
1. Cliquez sur **[!UICONTROL Télécharger]**.
1. Enregistrez le fichier de modèle sur votre système local.

   The template file is a tab-delimited data file ( [!DNL .tab] filename extension) that most spreadsheet applications support.

