---
title: Gestionnaire des tâches de classification
description: Découvrez comment afficher les tâches de classification en cours et terminées, générées à partir d’ensembles de classifications.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
feature: Classifications
source-git-commit: 77599d015ba227be25b7ebff82ecd609fa45a756
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 2%

---

# Afficher et agir sur les tâches de classification

Le gestionnaire des tâches de classification affiche les tâches de classification en cours et terminées qui sont générées pour les ensembles de classifications. Vous pouvez également utiliser le gestionnaire pour télécharger des données ou des modèles de classification pour une tâche spécifique.

Pour afficher et agir sur les tâches de classification, procédez comme suit :

1. Sélectionnez **[!UICONTROL Composants]** dans l’interface principale, puis sélectionnez **[!UICONTROL Ensembles de classifications]**.
1. Dans **[!UICONTROL Ensembles de classifications]**, sélectionnez l’onglet **[!UICONTROL Tâches]**.

## Gestionnaire des tâches de classification

Le gestionnaire **[!UICONTROL Ensembles de classifications - Tâches]** comporte les éléments d’interface suivants :

![Ensembles de classifications - Gestionnaire de tâches](manage/assets/classifications-sets-jobs.png)



### Liste des traitements de classification

La liste **[!UICONTROL Tâches de classification]** affiche ➊ les tâches de classification. La liste comporte les colonnes suivantes :

| Colonne | Description |
|---|---|
| **[!UICONTROL Identifiant de tâche]** | Identifiant de la tâche de classification. |
| **[!UICONTROL Ensemble de classifications]** | L’ensemble de classifications associé à la tâche de classification. |
| **[!UICONTROL Taille]** | Taille du fichier qui a été exporté ou importé dans le cadre de la tâche de classification. |
| **[!UICONTROL Statut]** | Statut de la tâche de classification. Les valeurs possibles sont les suivantes : **[!UICONTROL Created]**, **[!UICONTROL Queued]**, **[!UICONTROL Validated]**, **[!UICONTROL Failed validation]**, **[!UICONTROL Processing]**, **[!UICONTROL Done processing]**, **[!UICONTROL Failed processing]**, **[!UICONTROL Completed]** ou **[!UICONTROL Progress]**. |
| **[!UICONTROL Nom du fichier]** | Identifie le nom ou la fonctionnalité utilisée pour importer ou exporter le fichier dans le cadre de la tâche de classification. Les valeurs possibles sont les suivantes : <ul><li>*aucune valeur*</li><li>Nom du fichier qui est traité dans le cadre de la tâche de classification.</li><li>**[!UICONTROL Exportation SAINT]** : la tâche est une exportation à partir de l’interface [héritée Classifications](/help/components/classifications/importer/c-working-with-saint.md).</li><li>**[!UICONTROL export pour _jeu de classifications_ à _horodatage_]**: la tâche est un téléchargement depuis l’interface [schéma](manage/schema.md#download).</li></ul> |
| **[!UICONTROL Type de tâche]** | Type de tâche de classification. Les valeurs possibles sont les suivantes : **[!UICONTROL Importer]** ou **[!UICONTROL Exporter]**. |
| **[!UICONTROL Source]** | Source de la tâche de classification. Les valeurs possibles sont les suivantes : **[!UICONTROL API Web]**, **[!UICONTROL Chargement direct de l’API]**, **[!UICONTROL Adobe]**, **[!UICONTROL SAINT]** ou **[!UICONTROL Inconnu]**. |
| **[!UICONTROL Lignes modifiées]** | Nombre de lignes modifiées par la tâche de classification. |
| **[!UICONTROL Total des lignes]** | Nombre total de lignes traitées par la tâche de classification. |
| **[!UICONTROL Heure de fin]** | Heure d’achèvement de la tâche de classification. |
| **[!UICONTROL Téléchargement de fichier]** | Utilisez ![Télécharger](/help/assets/icons/Download.svg) pour télécharger le fichier (modèle ou données) associé à la tâche de classification. |

Pour redimensionner une colonne dans la liste des tâches de classification, vous pouvez :

* Pointez sur le séparateur de colonne et faites glisser le séparateur de colonne sur la largeur de colonne souhaitée.
* Sélectionnez ![ChevronDown](/help/assets/icons/ChevronDown.svg) puis **[!UICONTROL Redimensionner la colonne]**. Une ligne verticale avec le bouton de redimensionnement vous permet de redimensionner la colonne à l’aide de l’option souhaitée.

Pour trier une colonne dans la liste des tâches de classification, procédez comme suit :

* Sélectionnez ![ChevronDown](/help/assets/icons/ChevronDown.svg) et sélectionnez **[!UICONTROL Tri croissant]** ou **[!UICONTROL Tri décroissant]**. Une flèche (↑↓) indique quelle colonne et comment la colonne est triée.


### Boutons Rechercher et

Dans la zone ➋ en haut de la liste des tâches de classification, vous pouvez :

* Recherchez ![Rechercher](/help/assets/icons/Search.svg) les tâches de classification. Les résultats s’affichent dans la liste des tâches de classification. Sélectionnez ![CrossSize200](/help/assets/icons/CrossSize200.svg) pour effacer la recherche.
* Supprimez tout filtre appliqué à la liste des tâches de classification. Sélectionnez ![CrossSize100](/help/assets/icons/CrossSize100.svg) pour supprimer un filtre.
* Sélectionnez ![MoreCircle](/help/assets/icons/MoreCircle.svg) pour charger 1 000 tâches de classification supplémentaires. Au départ, la liste des ensembles de classifications affiche jusqu’à 1 000 tâches de classification.
* Définissez les colonnes de la liste des tâches des ensembles de classifications. Sélectionnez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) et, dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]**, sélectionnez les colonnes à afficher en dessous **[!UICONTROL Sélectionnez les colonnes à afficher]**. Sélectionnez **[!UICONTROL Appliquer]** pour appliquer les paramètres de colonne.



### Panneau Filtrer

Sélectionnez ![Filtrer](/help/assets/icons/Filter.svg) pour afficher la ➌ du panneau de filtrage qui vous permet de filtrer la liste des tâches de classification. Vous pouvez filtrer sur :

* **[!UICONTROL Ensemble de classifications]**. Sélectionnez un ou plusieurs ensembles de classifications pour filtrer la liste des tâches de classification.
* **[!UICONTROL Heure de fin]**. Sélectionnez l’une des valeurs possibles pour filtrer la liste des tâches de classification au moment de l’achèvement.
* **[!UICONTROL Statut]**. Sélectionnez l’une des valeurs possibles pour filtrer la liste des tâches de classification selon le statut.
* **[!UICONTROL Type de tâche]**. Sélectionnez l’une des valeurs possibles pour filtrer la liste des tâches de classification par type de tâche.
* **[!UICONTROL Source]**. Sélectionnez l’une des valeurs possibles pour filtrer la liste des tâches de classification sur la source.


Sélectionnez ![Filtrer](/help/assets/icons/Filter.svg) **[!UICONTROL Masquer les filtres]** pour masquer le panneau des filtres.

Notez que les filtres affichés dans le panneau Filtres reflètent les options des tâches de classification préchargées.


<!--

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Jobs]**

You cannot create jobs from this interface. Create jobs by uploading data to a classification set (either manually or through a configured external location), requesting a download file, or requesting a template file.

## Filter classification sets

The left side of the Classification set job manager provides filter settings to locate the desired job. Clicking the filter icon toggles the filter settings visibility. You can filter Classification sets by **[!UICONTROL Classification set]**, **[!UICONTROL Completion time]**, **[!UICONTROL Status]**, **[!UICONTROL Job Type]**, or **[!UICONTROL Source]**.

![Classification set job filters](../assets/classification-set-job-filters.png)

Additional filter options are available above the Classification set job manager columns:

* **[!UICONTROL Search by title]**: Search for jobs by filename.
* **[!UICONTROL Load more]**: The Classification set job manager initially displays up to 1000 jobs. If more jobs exist, click this button to load 1000 more jobs.
* **Show/Hide columns**: Toggle visibility for any column besides [!UICONTROL Filename] and [!UICONTROL Completion time].

## Classification set job manager columns

The following columns are available in the Classification set job manager:

* **[!UICONTROL Filename]**: The name of the upload or download file.
* **[!UICONTROL Classification set]**: The name of the Classification set that the file applies to. You can click the Classification set name to reach the Classification set's [Settings](manage/settings.md).
* **[!UICONTROL Size]**: The size of the file.
* **[!UICONTROL Status]**: The status of the job processing the file.
  * **[!UICONTROL Created]**: The job was submitted.
  * **[!UICONTROL Queued]**: The file is ready to be processed, and is waiting for a classification server to process the file.
  * **[!UICONTROL Validated]**: The file is valid and is waiting to be processed.
  * **[!UICONTROL Failed validation]**: The file is formatted incorrectly or otherwise invalid. The file does not go through processing.
  * **[!UICONTROL Processing]**: The file is actively being processed by Adobe.
  * **[!UICONTROL Failed processing]**: The file failed processing.
  * **[!UICONTROL Complete]**: Processing is complete. Classification data is visible in reporting.
  * **[!UICONTROL Failed]**: Generic failure not related to validation or processing.
* **[!UICONTROL Job type]**: The type of job.
* **[!UICONTROL Source]**: The job source.
* **[!UICONTROL File download]**: Only applies to download jobs, such as downloading classification data or downloading templates. When a download is ready, this column provides a download link.
* **[!UICONTROL Modified lines]**: The number of modified lines.
* **[!UICONTROL Completed lines]**: The number of completed lines.
* **[!UICONTROL Completion time]**: The date and time that the job completed (or failed).
-->