---
title: Gérer les ensembles de classifications
description: Gérez les ensembles de classifications dans Adobe Analytics.
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
feature: Classifications
source-git-commit: cfa8335008548254786e46dfe634229edad5bd54
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 5%

---

# Gérer des jeux de classifications

Vous pouvez créer, renommer, modifier, consolider, supprimer et baliser des ensembles de classifications dans l’interface de gestion des ensembles de classifications. Vous pouvez également filtrer par et rechercher des ensembles de classifications spécifiques.

Pour gérer les ensembles de classifications :

1. Sélectionnez **[!UICONTROL Composants]** dans la barre de menus supérieure d’Adobe Analytics, puis sélectionnez **[!UICONTROL Ensembles de classifications]**.
1. Dans **[!UICONTROL Ensembles de classifications]**, sélectionnez l’onglet **[!UICONTROL Ensembles de classifications]**.

## Gestionnaire des ensembles de classifications

Le gestionnaire **[!UICONTROL Ensembles de classifications]** comporte les éléments d’interface suivants :

![&#x200B; Gestionnaire des ensembles de classifications &#x200B;](assets/classification-sets-manage.png)


### Liste des ensembles de classifications

La **[!UICONTROL de liste]** Ensembles de classifications➊ affiche tous les ensembles de classifications. La liste comporte les colonnes suivantes :

| Colonne | Description |
|---|---|
| **[!UICONTROL Ensemble de classifications]** | Nom de l’ensemble de classifications. Sélectionnez le nom [modifier l’ensemble de classifications](create.md#edit-a-classification-set). |
| **[!UICONTROL Abonnements]** | Le nombre d’abonnements auxquels l’ensemble de classifications s’applique. |
| **[!UICONTROL Classifications]** | Le nombre de dimensions de classification que l’ensemble de classifications contient. |
| **[!UICONTROL Automatisé]** | L’ensemble de classifications est-il configuré pour importer automatiquement des données d’un emplacement cloud ou non ? Cette automatisation peut être configurée dans le cadre du [schéma des ensembles de classifications](manage/schema.md). |
| **[!UICONTROL Dernière modification]** | Date et heure de la dernière modification de l’ensemble de classifications. |

Pour redimensionner une colonne dans la liste des ensembles de classifications, vous pouvez :

* Pointez sur le séparateur de colonne et faites glisser le séparateur de colonne sur la largeur de colonne souhaitée.
* Sélectionnez ![ChevronDown](/help/assets/icons/ChevronDown.svg) puis **[!UICONTROL Redimensionner la colonne]**. Une ligne verticale avec le bouton de redimensionnement vous permet de redimensionner la colonne à l’aide de l’option souhaitée.

Pour trier une colonne dans la liste des ensembles de classifications, procédez comme suit :

* Sélectionnez ![ChevronDown](/help/assets/icons/ChevronDown.svg) et sélectionnez **[!UICONTROL Tri croissant]** ou **[!UICONTROL Tri décroissant]**. Une flèche (↑↓) indique quelle colonne et comment la colonne est triée.

### Boutons Rechercher et

Dans la zone ➋ en haut de la liste des ensembles de classifications, vous pouvez :

* Recherchez des ensembles de classifications ![Search](/help/assets/icons/Search.svg). Les résultats s’affichent dans la liste des ensembles de classifications. Sélectionnez ![CrossSize200](/help/assets/icons/CrossSize200.svg) pour effacer la recherche.
* Supprimez tout filtre appliqué à la liste des jeux de classifications. Sélectionnez ![CrossSize100](/help/assets/icons/CrossSize100.svg) pour supprimer un filtre.
* Sélectionnez ![MoreCircle](/help/assets/icons/MoreCircle.svg) pour charger 1 000 ensembles de classifications supplémentaires. Au départ, la liste des ensembles de classifications affiche jusqu’à 1 000 ensembles de classifications.
* Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]** pour [créer un ensemble de classifications](create.md#create-a-classification-set).
* Définissez les colonnes de la liste des ensembles de classifications. Sélectionnez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) et, dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]**, sélectionnez les colonnes à afficher en dessous **[!UICONTROL Sélectionnez les colonnes à afficher]**. Sélectionnez **[!UICONTROL Appliquer]** pour appliquer les paramètres de colonne.


### Barre d’actions

Lorsque vous sélectionnez un ou plusieurs ensembles de classifications dans la liste des ensembles de classifications, une barre d’actions bleue s’affiche ➌. Les actions suivantes sont disponibles dans la barre d’actions :

| Icône | Action | Description |
|---|---|---|
| ![Modifier](/help/assets/icons/Edit.svg) | **[!UICONTROL Modifier]** | [Modifiez l’ensemble de classifications](create.md#edit-a-classification-set) dans le créateur d’ensembles de classifications. |
| ![Renommer](/help/assets/icons/Rename.svg) | **[!UICONTROL Renommer]** | Renommez un ensemble de classifications.<br/>Dans la boîte de dialogue **[!UICONTROL Renommer : _ensemble de classifications_]**&#x200B;saisissez un nouveau nom et sélectionnez **[!UICONTROL Renommer]**. |
| ![Fusionner](/help/assets/icons/Merge.svg) | **[!UICONTROL Consolider]** | [Consolidez les ensembles de classifications](/help/components/classifications/sets/consolidations/manage.md). |
| ![Supprimer](/help/assets/icons/Delete.svg) | **[!UICONTROL Supprimer]** | Supprimez un ensemble de classifications.<br/>Le **[!UICONTROL Supprimer _jeu de classifications_ ?]** boîte de dialogue s’affiche. La suppression d’un ensemble de classifications ne peut pas être annulée. Tous les projets planifiés ou toutes les consolidations qui utilisent cet ensemble de classifications continuent à utiliser la définition de cet ensemble de classifications jusqu’à ce que vous réenregistriez les projets planifiés ou que vous validiez à nouveau les consolidations planifiées. Sélectionnez **[!UICONTROL Supprimer]** pour supprimer l’ensemble de classifications. |
| ![Libellé](/help/assets/icons/Label.svg) | **[!UICONTROL Étiquette]** | Balisez l’ensemble de classifications.<br/>Dans la boîte de dialogue **[!UICONTROL Balise : _jeu de classifications_]**, sélectionnez une ou plusieurs balises dans le menu déroulant **[!UICONTROL Balises]**&#x200B;pour ajouter des balises. Vous pouvez également saisir une ou plusieurs nouvelles balises. Utilisez ![CrossSize100](/help/assets/icons/CrossSize100.svg) pour supprimer une balise. <br/>Sélectionnez **[!UICONTROL Enregistrer]**&#x200B;pour enregistrer les balises. |


### Panneau Filtrer

Sélectionnez ![Filtrer](/help/assets/icons/Filter.svg) pour afficher la ➍ du panneau de filtrage qui vous permet de filtrer la liste des ensembles de classifications. Vous pouvez filtrer sur :

* **[!UICONTROL Balises]**. Sélectionnez une ou plusieurs balises pour filtrer la liste des ensembles de classifications sur les balises.
* **[!UICONTROL Suite de rapports]**. Sélectionnez une ou plusieurs suites de rapports pour filtrer la liste des jeux de classifications sur les suites de rapports.

Sélectionnez ![Filtrer](/help/assets/icons/Filter.svg) **[!UICONTROL Masquer les filtres]** pour masquer le panneau des filtres.

Notez que les filtres affichés dans le panneau Filtres reflètent les options des ensembles de classifications préchargés.
