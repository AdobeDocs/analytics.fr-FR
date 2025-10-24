---
title: Gérer les consolidations des ensembles de classifications
description: Découvrez comment consolider un ou plusieurs ensembles de classifications en un seul ensemble.
exl-id: 0be97ca4-56c3-4642-9347-924812e88e8c
feature: Classifications
source-git-commit: 77599d015ba227be25b7ebff82ecd609fa45a756
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 3%

---

# Gestion des consolidations de classification

Si vous disposez de plusieurs ensembles de classifications contenant des données de classification similaires, vous pouvez les consolider en un seul ensemble de classifications. Lorsque vous consolidez plusieurs ensembles de classifications, Adobe génère un nouvel ensemble de classifications qui contient toutes les données de classification de chaque ensemble de classifications. Les consolidations sont utiles lorsque vous avez chargé des données dans de nombreuses suites de rapports. Ou lorsque vous disposez de dimensions contenant les mêmes données de classification et que vous souhaitez les fusionner en un seul workflow.

Vous devez disposer d’un accès administrateur de produit pour Adobe Analytics afin de voir le gestionnaire de consolidation des ensembles de classifications.



Pour gérer les consolidations de classification :

1. Sélectionnez **[!UICONTROL Composants]** dans l’interface principale, puis sélectionnez **[!UICONTROL Ensembles de classifications]**.
1. Dans **[!UICONTROL Ensembles de classifications]**, sélectionnez l’onglet **[!UICONTROL Consolidations]**.


## Gestionnaire des consolidations de classification

Le gestionnaire **[!UICONTROL Ensembles de classifications - Consolidations]** comporte les éléments d’interface suivants :

![Jeux de classifications - Gestionnaire de consolidations](assets/classifications-sets-consolidations.png)



### Liste des consolidations de classification

La liste ➊ affiche les consolidations de classification créées et validées, et qui peuvent être en cours de consolidation. La liste comporte les colonnes suivantes :

| Colonne | Description |
|---|---|
| **[!UICONTROL Nom de la consolidation]** | Nom de la consolidation des ensembles de classifications. |
| **[!UICONTROL Tâche actuelle]** | Tâche associée à la consolidation des ensembles de classifications. |
| **[!UICONTROL Statut]** | Statut de la consolidation des ensembles de classifications. Les valeurs possibles sont les suivantes : **[!UICONTROL Créé]**, **[!UICONTROL Annulé]**, **[!UICONTROL Annulation]**, **[!UICONTROL Validation]**, **[!UICONTROL Échec de la validation]**, **[!UICONTROL Validé]**, **[!UICONTROL Comparaison]**, **[!UICONTROL Échec de la comparaison]**, **[!UICONTROL Submitted]**, **[!UICONTROL Consolidation]**, **[!UICONTROL Échec de la consolidation]**, **[!UICONTROL Consolidation réussie]**, **[!UICONTROL En attente de l’approbation]**, **[!UICONTROL Finalizing]**, **[!UICONTROL Échec]** ou **[!UICONTROL Completed]** **&#x200B;**. |
| **[!UICONTROL Heure de création]** | Heure de création de la consolidation des ensembles de classifications. |
| **[!UICONTROL Heure de fin]** | Heure d’achèvement des consolidations de classification. |


Pour redimensionner une colonne de la liste de consolidation des classifications, vous pouvez :

* Pointez sur le séparateur de colonne et faites glisser le séparateur de colonne sur la largeur de colonne souhaitée.
* Sélectionnez ![ChevronDown](/help/assets/icons/ChevronDown.svg) puis **[!UICONTROL Redimensionner la colonne]**. Une ligne verticale avec le bouton de redimensionnement vous permet de redimensionner la colonne à l’aide de l’option souhaitée.

Pour trier une colonne dans la liste de consolidation des classifications, procédez comme suit :

* Sélectionnez ![ChevronDown](/help/assets/icons/ChevronDown.svg) et sélectionnez **[!UICONTROL Tri croissant]** ou **[!UICONTROL Tri décroissant]**. Une flèche (↑↓) indique quelle colonne et comment la colonne est triée.

### Boutons Rechercher et

Dans la zone ➋ en haut de la liste des consolidations de classification, vous pouvez :

* Recherchez ![Rechercher](/help/assets/icons/Search.svg) des consolidations de classification. Les résultats s’affichent dans la liste des consolidations de classification. Sélectionnez ![CrossSize200](/help/assets/icons/CrossSize200.svg) pour effacer la recherche.
* Supprimez tout filtre appliqué à la liste de consolidation des ensembles de classifications. Sélectionnez ![CrossSize100](/help/assets/icons/CrossSize100.svg) pour supprimer un filtre.
* Créez une consolidation des ensembles de classifications. Sélectionnez ![AjouterCercle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Nouveau]** pour ouvrir la boîte de dialogue de consolidation des ensembles de classifications et définir une nouvelle consolidation des ensembles de classifications.
* Définissez les colonnes de la liste des consolidations de classification. Sélectionnez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) et, dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]**, sélectionnez les colonnes à afficher en dessous **[!UICONTROL Sélectionnez les colonnes à afficher]**. Sélectionnez **[!UICONTROL Appliquer]** pour appliquer les paramètres de colonne.


### Barre d’actions

Lorsque vous sélectionnez un ou plusieurs ensembles de classifications dans la liste des ensembles de classifications, une barre d’actions bleue s’affiche ➌. Les actions suivantes sont disponibles dans la barre d’actions :

| Icône | Action | Description |
|---|---|---|
| ![Modifier](/help/assets/icons/Edit.svg) | **[!UICONTROL Modifier]** | [Modifiez la consolidation des ensembles de classifications](process.md#edit-a-consolidation) |
| ![ViewDetail](/help/assets/icons/ViewDetail.svg) | **[!UICONTROL Affichage]** | Affichez les détails de la consolidation de l’ensemble de classifications. Selon le statut, vous pouvez [approuver](process.md#approve) ou [annuler](process.md#cancel) la consolidation. |


### Panneau Filtrer

Sélectionnez ![Filtrer](/help/assets/icons/Filter.svg) pour afficher la ➍ du panneau de filtrage qui vous permet de filtrer la liste des consolidations de classification. Vous pouvez filtrer sur :

* **[!UICONTROL Statut]**. Sélectionnez l’une des valeurs possibles pour filtrer la liste des consolidations de classification selon le statut. |
* **[!UICONTROL Heure de fin]**. Sélectionnez l’une des valeurs possibles pour filtrer la liste des consolidations de classification à l’heure d’achèvement.
* **[!UICONTROL Heure de création]**. Sélectionnez l’une des valeurs possibles pour filtrer la liste des consolidations de classification à l’heure d’achèvement.


Sélectionnez ![Filtrer](/help/assets/icons/Filter.svg) **[!UICONTROL Masquer les filtres]** pour masquer le panneau des filtres.

Notez que les filtres affichés dans le panneau Filtres reflètent les options des consolidations de classification préchargées.


<!--

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Consolidations]**

Once a consolidation is run, the original classification sets are removed, with the consolidated classification set taking their place. Click **[!UICONTROL Add]** to [Create a consolidation](process.md).

## Filter classification sets

The left side of the Classification set consolidation manager provides filter settings to locate the desired consolidation. Clicking the filter icon toggles the filter settings visibility. You can filter consolidations by **[!UICONTROL Status]**, **[!UICONTROL Completion time]**, or **[!UICONTROL Creation time]**.

![Classification set consolidation filters](../../assets/classification-set-consolidation-filters.png)

Additional filter options are available above the Classification set consolidation manager columns:

* **[!UICONTROL Search by title]**: Search for consolidations by name.
* **Show/Hide columns**: Toggle visibility for any column besides [!UICONTROL Name].

## Classification set consolidation manager columns

The following columns are available in the Classification set consolidation manager:

* **[!UICONTROL Name]**: The name of the consolidation.
* **[!UICONTROL Current job]**: The current job. 
* **[!UICONTROL Status]**: The status of the consolidation. 
* **[!UICONTROL Creation date]**: The date and time that the consolidation was created.
* **[!UICONTROL Completion date]**: The date and time that the consolidation completed (or failed).

-->
