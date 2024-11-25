---
title: Comment gérer les blocs de données à l’aide de Report Builder
description: Décrit comment utiliser la fonction de gestion dans Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 63e169b3-7e13-405e-83a4-17f2a9917ed2
source-git-commit: 8c863329e385c7e3fe15d85c07e1a1d541296acb
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 57%

---

# Gérer les blocs de données dans Report Builder

Vous pouvez afficher et gérer tous les blocs de données d’un classeur à l’aide du Gestionnaire de blocs de données. Le Gestionnaire de blocs de données fournit des fonctionnalités de recherche, de filtrage et de tri qui vous permettent de localiser rapidement des blocs de données spécifiques. Après avoir sélectionné un ou plusieurs blocs de données, vous pouvez modifier, supprimer ou actualiser les blocs de données sélectionnés.

![Écran du gestionnaire de blocs de données.](./assets/image52.png)

## Afficher les blocs de données

Cliquez sur **Gérer** pour afficher la liste de tous les blocs de données d’un classeur.

![ L&#39;option Gérer pour afficher une liste de tous les blocs de données.](./assets/image53.png)

Le Gestionnaire de blocs de données répertorie tous les blocs de données présents dans un classeur. 

## Trier la liste Blocs de données

Vous pouvez trier la liste Blocs de données par colonne affichée. Vous pouvez, par exemple, trier la liste bloquée de données par suites de rapports, segments, période et autres variables.

Pour trier la liste Blocs de données, cliquez sur un en-tête de colonne.

![Tri des blocs de données.](./assets/image54.png)

## Rechercher dans la Liste Blocs de données

Utilisez le champ Rechercher pour localiser tout élément dans le tableau des blocs de données. Par exemple, vous pouvez rechercher les mesures contenues dans les blocs de données ou la suite de rapports. Vous pouvez également rechercher des dates apparaissant dans les colonnes de périodes, de date de modification ou de date de dernière exécution.

![Utilisation du champ Rechercher pour localiser n’importe quoi dans la table de bloc de données.](./assets/image55.png)

## Modifier les blocs de données

Vous pouvez modifier la suite de rapports, la période ou les segments appliqués à un ou plusieurs blocs de données.

Par exemple, vous pouvez remplacer un segment existant par un nouveau segment dans un ou plusieurs blocs de données.

1. Sélectionnez les blocs de données à mettre à jour. Vous pouvez cocher la case de niveau supérieur pour sélectionner tous les blocs de données ou sélectionner des blocs de données individuels.

   ![Icône de modification de crayon](./assets/image56.png)

1. Cliquez sur l’icône d’édition pour afficher la fenêtre Modification rapide.

   ![La fenêtre de modification rapide](./assets/image58.png)

1. Sélectionnez un lien de segment pour mettre à jour les suites de rapports, les périodes ou les segments.

   ![Le champ Ajouter un segment dans la fenêtre d’édition rapide](./assets/image59.png)

## Actualiser les blocs de données

Cliquez sur l’icône d’actualisation pour actualiser les blocs de données de la liste.

<img src="./assets/refresh-icon.png" width="15%" alt="Icône Actualiser"/>

Pour vérifier si un bloc de données est actualisé, cliquez sur l’icône Actualiser l’état .

Un bloc de données correctement actualisé affiche une coche dans un cercle vert : <img src="./assets/refresh-success.png" width="5%" alt="Cercle vert avec icône de coche"/>.

Un bloc de données qui n’a pas été actualisé affiche une icône d’avertissement : <img src="./assets/refresh-failure.png" width="5%" alt="Triangle rouge avec icône de point d’exclamation"/>. Cela permet d’identifier facilement si des blocs de données comportent des erreurs.


![Gestionnaire de blocs de données présentant l’état d’actualisation de chaque bloc de données répertorié.](./assets/image512.png)

## Supprimer un bloc de données

1. Sélectionnez un bloc de données dans le gestionnaire de blocs de données.
1. Cliquez sur l&#39;icône représentant une corbeille pour supprimer le bloc de données sélectionné.

## Regrouper les blocs de données

Vous pouvez regrouper des blocs de données à l’aide de la variable **Grouper par** ou cliquer sur le titre d’une colonne. Pour trier les blocs de données par colonne, cliquez sur le titre de la colonne. Pour regrouper des blocs de données par groupes, sélectionnez un nom de groupe dans le menu déroulant **Grouper par**. Par exemple, la capture d’écran ci-dessous présente les blocs de données regroupés par feuille. Elle affiche les blocs de données regroupés par Feuille1 et Feuille2. Cela s’avère utile, par exemple, dans le cas d’utilisation du remplacement de segment. Si plusieurs segments sont appliqués à chaque bloc de données, il est utile de créer un groupe contenant tous les blocs de données à remplacer. Vous pouvez ensuite facilement les sélectionner et les modifier tous en même temps.

![Gestionnaire de blocs de données affichant la liste Groupe par feuille.](./assets/group-data-blocks.png)

## Modifier la vue Gestionnaire de blocs de données

Vous pouvez modifier les colonnes visibles dans la fenêtre Gestionnaire de blocs de données.


Cliquez sur l’icône de la liste des colonnes <img src="./assets/image515.png" width="3%" alt="Icône Liste des colonnes"/> pour sélectionner les colonnes répertoriées dans le Gestionnaire de blocs de données. Sélectionnez le nom de la colonne à afficher. Désélectionnez le nom de la colonne pour la supprimer de la vue.

![Gestionnaire de blocs de données présentant la liste de colonnes](./assets/image516.png)
