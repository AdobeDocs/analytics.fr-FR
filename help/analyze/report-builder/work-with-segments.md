---
title: Utilisation des segments dans Report Builder dans Adobe Analytics
description: Décrit comment utiliser des segments dans Report Builder pour Adobe Analytics
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: eedabc6295f9b918e1e00b93993680e676c216c3
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 4%

---

# Utilisation des segments dans Report Builder

Vous pouvez appliquer des segments lorsque vous créez un bloc de données ou lorsque vous sélectionnez l’option **Modifier le bloc de données** dans le panneau COMMANDES.

## Application de segments à un bloc de données

Pour appliquer un segment à l’ensemble du bloc de données, double-cliquez sur un segment ou effectuez un glisser-déposer de filtres depuis la liste de composants vers la section Segments du tableau.

## Application de segments à des mesures individuelles

Pour appliquer des segments à des mesures individuelles, faites glisser un segment sur une mesure du tableau. Vous pouvez également cliquer sur l’icône **...** située à droite d’une mesure dans le volet Tableau, puis sélectionner **Mesure du segment**. Pour afficher les segments appliqués, survolez ou sélectionnez une mesure dans le volet Tableau . Les mesures avec les segments appliqués affichent une icône de filtre.

![Onglet Segments affichant des mesures.](./assets/filter_by.png)

## Modification rapide des segments

Vous pouvez utiliser le panneau Modification rapide pour ajouter, supprimer ou remplacer des segments pour des blocs de données existants.

Lorsque vous sélectionnez une plage de cellules dans la feuille de calcul, le lien **Segments** du panneau Modification rapide affiche une liste récapitulative des segments utilisés par les blocs de données de cette sélection.

Pour modifier des segments à l’aide du panneau Modification rapide

1. Sélectionnez une plage de cellules à partir dʼun ou de plusieurs blocs de données.

   ![ Panneau Modification rapide du segment présentant les options de segment pour les suites de rapports, la période et les segments.](./assets/select_multiple_dbs.png)

1. Cliquez sur le lien Segments pour lancer le panneau Modification rapide - Filtres .

   ![Panneau Segments affichant le champ Ajouter des segments et les listes Segments appliqués.](./assets/quick_edit_filters.png)

### Ajout ou suppression d’un segment

Vous pouvez ajouter ou supprimer des segments à l’aide des options Ajouter/Supprimer .

1. Sélectionnez l’onglet **Ajouter/Supprimer** dans le panneau Modification rapide des segments .

   Tous les segments appliqués aux blocs de données sélectionnés sont répertoriés dans le panneau Modification rapide des segments . Les segments appliqués à tous les blocs de données de la sélection sont répertoriés sous l’en-tête **Application à tous les blocs de données sélectionnés**. Les segments appliqués à certains blocs de données, mais pas tous, sont répertoriés sous l’en-tête **Application à 1 ou plusieurs blocs de données sélectionnés** .

   Lorsque plusieurs segments sont présents dans les blocs de données sélectionnés, vous pouvez rechercher des segments spécifiques à l’aide du champ de recherche **Ajouter un filtre** .

   ![Le champ Ajouter des segments.](./assets/add_filter.png)

1. Ajoutez des segments en sélectionnant des segments dans le menu déroulant **Ajouter un segment** .

   La liste des segments pouvant faire l’objet d’une recherche comprend tous les segments accessibles aux suites de rapports présentes dans un ou plusieurs des blocs de données sélectionnés, ainsi que tous les segments disponibles globalement dans l’organisation.

   L’ajout d’un segment applique le segment à tous les blocs de données de la sélection.

1. Pour supprimer des segments, cliquez sur l’icône de suppression **x** située à droite des segments dans la liste **Segments appliqués**.

1. Cliquez sur **Appliquer** pour enregistrer les modifications et revenir au panneau hub.

   Report Builder affiche un message pour confirmer les modifications de segment appliquées.

### Remplacement d’un segment

Vous pouvez remplacer un segment existant par un autre segment pour modifier la manière dont les données sont segmentées.

1. Sélectionnez l’onglet **Remplacer** dans le panneau Modification rapide - segment .

   ![Sélectionnez l’onglet Remplacer.](./assets/replace_filter.png)

1. Utilisez le champ de recherche **Liste de recherche** pour localiser des segments spécifiques.

1. Sélectionnez un ou plusieurs segments à remplacer.

1. Recherchez un ou plusieurs segments dans le champ Remplacer par .

   La sélection dʼun filtre lʼajoute à la liste **Remplacer par**...

   ![L’onglet Remplacer par le bloc de données Personnes sur l’application sélectionné et la liste Remplacer par mise à jour affichant Personnes sur l’application révisées.](./assets/replace_screen_new.png)

1. Cliquez sur **Appliquer**.

   Report Builder met à jour la liste des segments pour refléter le remplacement.

### Définition des segments de bloc de données à partir d’une cellule

Les blocs de données peuvent référencer des segments à partir d’une cellule. Plusieurs blocs de données peuvent référencer la même cellule pour les segments, ce qui vous permet de changer facilement de segment pour plusieurs blocs de données à la fois.

Pour appliquer des segments depuis une cellule

1. Accédez à l’étape 2 dans le processus de création ou d’édition du bloc de données. Voir [Création d’un bloc de données](./create-a-data-block.md).
1. Cliquez sur l’onglet **Segments** pour définir des filtres.
1. Cliquez sur **Créer un segment à partir de la cellule**.

   ![Créer un segment à partir de l’icône de cellule.](./assets/create-filter-from-cell.png)

1. Sélectionnez la cellule à partir de laquelle vous souhaitez que les blocs de données référencent un segment.

1. Ajoutez le choix de segment que vous souhaitez ajouter à la cellule en double-cliquant sur le segment ou en le faisant glisser et en le déposant dans la section Segments inclus .

   Remarque : Un seul choix peut être sélectionné simultanément pour la cellule donnée.

   ![La fenêtre Ajouter un segment à partir de la cellule qui affiche les filtres inclus.](./assets/select-filters.png)

1. Cliquez sur **Apply** pour créer la cellule de référence.

1. Dans l’onglet **Segments** , ajoutez les segments de cellule de référence nouvellement créés à votre bloc de données.

   ![Onglet Segments présentant le segment Sheet1!J1(Toutes les données) ajouté à la table.](./assets/reference-cell-filter.png)

1. Cliquez sur **Terminer**.

   Désormais, cette cellule peut être référencée par d’autres blocs de données dans leurs segments. Pour appliquer la cellule de référence en tant que segment à d’autres blocs de données, ajoutez simplement la référence de cellule à leurs segments à partir de l’onglet Segments .

#### Utilisation de la cellule de référence pour modifier les segments de bloc de données

1. Sélectionnez la cellule de référence dans votre feuille de calcul.

1. Cliquez sur le lien sous **Segments de la cellule** dans le menu Modification rapide.

   ![ Segments à partir d’un lien de cellule affichant Sheet1!J1 (Toutes les données)](./assets/filters-from-cell-link.png)

1. Sélectionnez votre segment dans le menu déroulant.

   ![Menu déroulant Segments](./assets/filter-drop-down.png)

1. Cliquez sur **Appliquer**.
