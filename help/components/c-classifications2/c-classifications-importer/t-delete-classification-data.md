---
description: Description de la procédure de suppression des données de classification.
seo-description: Description de la procédure de suppression des données de classification.
seo-title: Suppression des données de classification
solution: Analytics
subtopic: Classifications
title: Suppression des données de classification
topic: Outils d’administration
uuid: 5b1b0ac7-ee52-4fd8-b98e-25283595cf0c
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Suppression des données de classification

Description de la procédure de suppression des données de classification.

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Browser Export]**.
1. Sélectionnez la suite de rapports et le jeu de données duquel vous souhaitez supprimer des données de classification.
1. Adjust any optional settings to filter specific data you're looking for, then click **[!UICONTROL Export File]**.
1. Once the file has been downloaded, open the file and replace any classification values you wish to delete with [!DNL ~empty~].

   Alternatively, use [!DNL ~deletekey~]. Cette commande traite la classification comme si elle ne s’était jamais produite pour la clé spécifiée. Elle supprime complètement la classification, ainsi que toute donnée de colonne, des tableaux de recherche.

   **Avertissement**: Vous n'avez besoin que d'une colonne contenant [!DNL ~deletekey~]. The [!DNL ~empty~] command works at the cell level (key and column combination), so you need [!DNL ~empty~] in the classification column you want to remove. However, [!DNL ~deletekey~] works at the row level (the key and all associated metadata), so it only needs to appear in one of the columns in the row. Cette commande supprime toutes les métadonnées de la ligne. Adobe interprète cela comme si la clé n’avait jamais été classée et l’affiche dans la catégorie [Aucun](/help/components/c-classifications2/c-classifications-importer/nonclassified-keys.md#concept_233E51DDF3084FF7B7EA89381C73C5FF).

1. Enregistrez le fichier et téléchargez-le à l’aide de l’onglet [!UICONTROL Importer un fichier.]

   After you upload the file, the system recognizes [!DNL ~empty~] as a command to delete that classification value.

   **Propriétés de cette commande**

* [!DNL ~empty~] doit être en minuscules sans espaces. Les entrées suivantes ne sont pas valides :

   * [!DNL ~EMPTY~]
   * [!DNL ~ empty ~]
   * [!DNL ~Empty~]

* Vous ne pouvez pas supprimer les valeurs d’une colonne de clé. Il s’agit des données transmises directement à la création de rapports et qui sont permanentes.
* Si vous supprimez une valeur de classification qui comporte des sous-classifications, ces dernières sont également supprimées. Les classifications ne peuvent pas exister sans valeur de clé et le parent d’une sous-classification est sa propre valeur de clé.
* Il est possible de supprimer des données de classification sans modifier sa classification parent.

