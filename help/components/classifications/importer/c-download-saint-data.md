---
description: (Facultatif) Avant d’importer des classifications dans des rapports marketing, vous pouvez télécharger un modèle qui vous aide à créer un fichier de données de classification. Ce fichier de données utilise les classifications voulues sous la forme d’en-têtes de colonne, puis classe le jeu de données de rapport sous les en-têtes de classification adéquats.
title: Modèle de classification
feature: Classifications
exl-id: e299509a-0c4f-4ba8-9e91-96356c386054
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 99%

---

# Modèle de classification (hérité)

(Facultatif) Avant d’importer des classifications dans des rapports et des projets, vous pouvez télécharger un modèle qui vous aide à créer un fichier de données de classification. Ce fichier de données utilise les classifications voulues sous la forme d’en-têtes de colonne, puis classe le jeu de données de rapport sous les en-têtes de classification adéquats.

## Modèle de classification {#concept_0F06847AD8D042F5BA818AE3C37E2417}

(Facultatif) Avant d’importer des classifications dans des rapports marketing, vous pouvez télécharger un modèle qui vous aide à créer un fichier de données de classification. Ce fichier de données utilise les classifications voulues sous la forme d’en-têtes de colonne, puis classe le jeu de données de rapport sous les en-têtes de classification adéquats.

**[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**.

| Élément | Description |
| --- | ---|
| Sélectionner une suite de rapports | Sélectionnez la suite de rapports à utiliser dans le modèle. La suite de rapports et l’ensemble de données doivent correspondre. |
| Données à classer | Sélectionnez le type de données pour le fichier de données. Le menu comprend tous les rapports des suites de rapports qui sont configurés pour les classifications. |
| Exporter Numérique 2 | **Important** : cette option n’est pas disponible pour les suites de rapports activées pour la nouvelle architecture de classification. |
| Encodage | Sélectionnez le codage des caractères pour le fichier de données. Le format de codage par défaut est UTF-8.<br>**Important** : cette option n’est pas disponible pour les suites de rapports activées pour la nouvelle architecture de classification. |
| Télécharger | Télécharge le fichier de modèle. |

Ce modèle comprend les classifications actuellement définies (en-têtes de colonne) pour un ensemble de données spécifiques sans inclure les données associées à chaque classification.

>[!NOTE]
>
>La méthode Modèle limite le téléchargement des données de classification à une seule suite de rapports.

Pour plus d’informations sur la structure d’un fichier de données, consultez la section [À propos des fichiers de données de classification](/help/components/classifications/importer/c-saint-data-files.md).

## Télécharger un modèle de données de classification (facultatif) {#task_8DFCF309B6FD43ABB1D6FEE9AFAEC596}

Le modèle fournit le format de fichier que vous devez respecter pour les classifications.

>[!NOTE]
>
>La méthode Modèle limite le téléchargement des données à une seule suite de rapports.

1. Cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**.
1. Sous l’onglet **[!UICONTROL Télécharger un modèle]**, spécifiez la [configuration du modèle de données](/help/components/classifications/importer/c-download-saint-data.md).
1. Cliquez sur **[!UICONTROL Télécharger]**.
1. Enregistrez le fichier de modèle sur votre système local.

   Le fichier de modèle est un fichier de données délimité par des tabulations (extension de nom de fichier [!DNL .tab] ) qui est pris en charge par la plupart des tableurs.
