---
title: Utilisation des segments dans le Report Builder dans Adobe Analytics
description: Décrit comment utiliser des segments en Report Builder pour Adobe Analytics
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 2691fde0-59c6-45a7-80a5-8e5e221adce2
source-git-commit: 2cb8f72a37699aa45135c9d26686f93ee20f20d7
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 4%

---

# Utilisation de segments dans le Report Builder

Vous pouvez appliquer des segments lorsque vous créez un bloc de données ou lorsque vous sélectionnez l’option **Modifier le bloc de données** dans le panneau COMMANDES.

## Application de segments à un bloc de données

Pour appliquer un segment à l’ensemble du bloc de données, double-cliquez sur un segment ou faites glisser et déposez des filtres depuis la liste des composants vers la section Segments du tableau.

## Application de segments à des mesures individuelles

Pour appliquer des segments à des mesures individuelles, faites glisser et déposez un segment sur une mesure du tableau. Vous pouvez également cliquer sur l’icône **...** à droite d’une mesure dans le volet Tableau, puis sélectionner **[!UICONTROL Mesure du segment]**. Pour afficher les segments appliqués, survolez une mesure avec la souris ou sélectionnez-la dans le volet Tableau . Les mesures avec des segments appliqués affichent une icône de filtre.

![Onglet Segments affichant les mesures.](./assets/filter_by.png)

## Modification rapide de segments

Vous pouvez utiliser le panneau Modification rapide pour ajouter, supprimer ou remplacer des segments pour des blocs de données existants.

Lorsque vous sélectionnez une plage de cellules dans la feuille de calcul, le lien **[!UICONTROL Segments]** du panneau Modification rapide affiche une liste récapitulative des segments utilisés par les blocs de données dans cette sélection.

Pour modifier des segments à l’aide du panneau Modification rapide

1. Sélectionnez une plage de cellules à partir dʼun ou de plusieurs blocs de données.

   ![Panneau Modification rapide de segment présentant les options de segment pour les suites de rapports, les périodes et les segments.](./assets/select_multiple_dbs.png)

1. Cliquez sur le lien situé sous **[!UICONTROL Segments]** pour lancer le panneau Modification rapide - Filtres.

   ![le panneau Segments affichant le champ Ajouter des segments et les listes Segments appliqués ](./assets/quick_edit_filters.png).

### Ajout ou suppression d’un segment

Vous pouvez ajouter ou supprimer des segments à l’aide des options Ajouter/Supprimer .

1. Sélectionnez l’onglet **[!UICONTROL Ajouter/Supprimer]** dans le panneau Modification rapide - Segments.

   Tous les segments appliqués aux blocs de données sélectionnés sont répertoriés dans le panneau Modification rapide - Segments . Les segments appliqués à tous les blocs de données de la sélection sont répertoriés sous l’en-tête **[!UICONTROL Appliqué à tous les blocs de données sélectionnés]**. Les segments appliqués à certains blocs de données, mais pas à tous, sont répertoriés sous l’en-tête **[!UICONTROL Appliqué à un ou plusieurs blocs de données sélectionnés]**.

   Lorsque plusieurs segments sont présents dans les blocs de données sélectionnés, vous pouvez rechercher des segments spécifiques à l’aide du champ de recherche **[!UICONTROL Ajouter un filtre]**.

   ![Le champ Ajouter des segments.](./assets/add_filter.png)

1. Ajoutez des segments en les sélectionnant dans le menu déroulant **[!UICONTROL Ajouter un segment]**.

   La liste des segments pouvant faire l’objet d’une recherche inclut tous les segments accessibles aux suites de rapports qui sont présents dans un ou plusieurs des blocs de données sélectionnés, ainsi que tous les segments disponibles globalement dans l’organisation.

   L’ajout d’un segment applique le segment à tous les blocs de données de la sélection.

1. Pour supprimer des segments, cliquez sur l’icône de suppression **x** à droite des segments dans la liste **[!UICONTROL Segments appliqués]**.

1. Cliquez sur **[!UICONTROL Appliquer]** pour enregistrer les modifications et revenir au panneau hub.

   Report Builder affiche un message pour confirmer les modifications de segment appliquées.

### Remplacement d’un segment

Vous pouvez remplacer un segment existant par un autre segment pour modifier la manière dont les données sont segmentées.

1. Sélectionnez l’onglet **[!UICONTROL Remplacer]** dans le panneau Modification rapide-segment.

   ![Sélectionnez l’onglet Remplacer](./assets/replace_filter.png).

1. Utilisez le champ de recherche **[!UICONTROL Liste de recherche]** pour localiser des segments spécifiques.

1. Sélectionnez un ou plusieurs segments à remplacer.

1. Recherchez un ou plusieurs segments dans le champ Remplacer par .

   La sélection dʼun filtre lʼajoute à la liste **[!UICONTROL Remplacer par]**...

1. Cliquez sur **[!UICONTROL Appliquer]**.

   Le Report Builder met à jour la liste des segments pour refléter le remplacement.

### Définir des segments de blocs de données depuis la cellule

Les blocs de données peuvent référencer des segments à partir d’une cellule. Plusieurs blocs de données peuvent référencer la même cellule pour des segments, ce qui vous permet de changer facilement de segment pour plusieurs blocs de données à la fois.

Pour appliquer des segments depuis une cellule

1. Accédez à l’étape 2 dans le processus de création ou de modification de bloc de données. Voir [Création d’un bloc de données](./create-a-data-block.md).
1. Cliquez sur l’onglet **[!UICONTROL Segments]** pour définir des filtres.
1. Cliquez sur **[!UICONTROL Créer un segment à partir de la cellule]**.

   ![Icône Créer un segment à partir d’une cellule.](./assets/create-filter-from-cell.png)

1. Sélectionnez la cellule à partir de laquelle vous souhaitez que les blocs de données référencent un segment.

1. Ajoutez le choix de segment que vous souhaitez ajouter à la cellule en double-cliquant sur le segment ou en le faisant glisser et en le déposant dans la section **[!UICONTROL Segments inclus]**.

   Remarque : Un seul choix peut être sélectionné à la fois pour la cellule donnée.

   ![Fenêtre Ajouter un segment depuis la cellule affichant les filtres inclus.](./assets/select-filters.png)

1. Cliquez sur **[!UICONTROL Appliquer]** pour créer la cellule de référence.

1. Dans l’onglet **[!UICONTROL Segments]**, ajoutez les segments de cellule de référence nouvellement créés à votre bloc de données.

   ![Onglet Segments affichant le segment Sheet1!J1(All Data) ajouté au tableau.](./assets/reference-cell-filter.png)

1. Cliquez sur **[!UICONTROL Terminer]**.

   Désormais, cette cellule peut être référencée par d’autres blocs de données dans leurs segments. Pour appliquer la cellule de référence en tant que segment à d’autres blocs de données, ajoutez simplement la référence de cellule à leurs segments à partir de l’onglet Segments .

#### Utiliser la cellule de référence pour modifier les segments de bloc de données

1. Sélectionnez la cellule de référence dans votre feuille de calcul.

1. Cliquez sur le lien situé sous **[!UICONTROL Segments depuis la cellule]** dans le menu Modification rapide.

   ![Segments du lien de cellule affichant Sheet1!J1 (Toutes les données)](./assets/filters-from-cell-link.png)

1. Sélectionnez votre segment dans le menu déroulant.

   ![Menu déroulant Segments](./assets/filter-drop-down.png)

1. Cliquez sur **[!UICONTROL Appliquer]**.
