---
description: (Facultatif) Avant d’importer des classifications dans des rapports marketing, vous pouvez télécharger un modèle qui vous aide à créer un fichier de données de classification. Ce fichier de données utilise les classifications voulues sous la forme d’en-têtes de colonne, puis classe le jeu de données de rapport sous les en-têtes de classification adéquats.
title: Modèle de classification
feature: Classifications
exl-id: e299509a-0c4f-4ba8-9e91-96356c386054
TQID: https://experienceleague.adobe.com/OR9THCLd93iUl58npPiinO4yAsK8KG3FU8qmBILHioY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 355
ht-degree: 92%

---

# Modèle de classification (hérité)

{{classification-importer-deprecation}}

(Facultatif) Avant d’importer des classifications dans des rapports et des projets, vous pouvez télécharger un modèle qui vous aide à créer un fichier de données de classification. Ce fichier de données utilise les classifications voulues sous la forme d’en-têtes de colonne, puis classe le jeu de données de rapport sous les en-têtes de classification adéquats.

## Modèle de classification {#concept_0F06847AD8D042F5BA818AE3C37E2417}

(Facultatif) Avant d’importer des classifications dans des rapports marketing, vous pouvez télécharger un modèle qui vous aide à créer un fichier de données de classification. Ce fichier de données utilise les classifications voulues sous la forme d’en-têtes de colonne, puis classe le jeu de données de rapport sous les en-têtes de classification adéquats.

**[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**.

| Élément | Description |
| --- | ---|
| Sélectionner une suite de rapports | Sélectionnez la suite de rapports à utiliser dans le modèle. La suite de rapports et l’ensemble de données doivent correspondre. |
| Données à classer | Sélectionnez le type de données pour le fichier de données. Le menu comprend tous les rapports des suites de rapports qui sont configurés pour les classifications. |
| Exporter Numérique 2 | **Important** : cette option n’est pas disponible pour les suites de rapports activées pour la nouvelle architecture de classification. |
| Encodage | Sélectionnez le codage des caractères pour le fichier de données. Le format de codage par défaut est UTF-8.<br>**Important** : cette option n’est pas disponible pour les suites de rapports activées pour la nouvelle architecture de classification. |
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
