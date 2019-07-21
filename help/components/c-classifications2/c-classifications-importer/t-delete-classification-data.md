---
description: Description de la procédure de suppression des données de classification.
seo-description: Description de la procédure de suppression des données de classification.
seo-title: Supprimer des données de classification
solution: Analytics
subtopic: Gestionnaire
title: Supprimer des données de classification
topic: Outils d’administration
uuid: 5 b 1 b 0 ac 7-ee 52-4 fd 8-b 98 e -25283595 cf 0 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Supprimer des données de classification

Description de la procédure de suppression des données de classification.

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Browser Export]**.
1. Sélectionnez la suite de rapports et le jeu de données duquel vous souhaitez supprimer des données de classification.
1. Adjust any optional settings to filter specific data you're looking for, then click **[!UICONTROL Export File]**.
1. Once the file has been downloaded, open the file and replace any classification values you wish to delete with [!DNL ~empty~].

   Alternatively, use [!DNL ~deletekey~]. Cette commande traite la classification comme si elle ne s’était jamais produite pour la clé spécifiée. Elle supprime complètement la classification, ainsi que toute donnée de colonne, des tableaux de recherche.

   **Avertissement**: Il vous suffit d'une colonne contenant [!DNL ~la clé deletekey~]. The [!DNL ~empty~] command works at the cell level (key and column combination), so you need [!DNL ~empty~] in the classification column you want to remove. [!DNL ~Cependant, la clé deletekey~] fonctionne au niveau de la ligne (la clé et toutes les métadonnées associées) ; elle doit donc uniquement apparaître dans l'une des colonnes de la ligne. Cette commande supprime toutes les métadonnées de la ligne. Adobe interprète cela comme si la clé n’avait jamais été classée et l’affiche dans la catégorie [Aucun](../../../components/c-classifications2/c-classifications-importer/nonclassified-keys.md#concept_233E51DDF3084FF7B7EA89381C73C5FF).

1. Enregistrez le fichier et téléchargez-le à l’aide de l’onglet [!UICONTROL Importer un fichier.]

   After you upload the file, the system recognizes [!DNL ~empty~] as a command to delete that classification value.

   **Propriétés de cette commande**

* [!DNL ~vide~] doit être en minuscules sans espaces. Les entrées suivantes ne sont pas valides :

   * [!DNL ~EMPTY~]
   * [!DNL ~ empty ~]
   * [!DNL ~Empty~]

* Vous ne pouvez pas supprimer les valeurs d’une colonne de clé. Il s’agit des données transmises directement à la création de rapports et qui sont permanentes.
* Si vous supprimez une valeur de classification qui comporte des sous-classifications, ces dernières sont également supprimées. Les classifications ne peuvent pas exister sans valeur de clé et le parent d’une sous-classification est sa propre valeur de clé.
* Il est possible de supprimer des données de classification sans modifier sa classification parent.

