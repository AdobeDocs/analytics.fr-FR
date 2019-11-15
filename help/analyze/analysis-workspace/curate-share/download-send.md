---
description: Vous pouvez télécharger des projets enregistrés et non enregistrés au format PDF ou CSV.
title: Téléchargement de fichiers PDF ou CSV
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Téléchargement de fichiers PDF ou CSV

Vous pouvez télécharger des projets enregistrés et non enregistrés au format PDF ou CSV.

Le nom du fichier PDF ou CSV correspond au nom actuel du projet. Pour les projets non enregistrés, le fichier téléchargé comprend les modifications non enregistrées apportées au projet. Remarque : Vous ne pouvez pas planifier les projets non enregistrés au format PDF ou CSV.

> [!NOTE] Nous prenons également en charge la visualisation Abandons au format CSV.

> [!NOTE] Lorsque nous rendons un projet au format PDF, nous rendons simplement ce qui se trouve sur la page. Si un projet comprend des panneaux et des visualisations aux dimensions personnalisées, vous devez définir leurs dimensions automatiquement (à l’aide du bouton dans le coin supérieur droit) afin d’éviter toute troncation du contenu.

1. Créez ou ouvrez un projet.
1. Click **[!UICONTROL Project]** &gt; **[!UICONTROL Download CSV (or Download PDF).]**

On April 11, 2019, several changes were made to **[!CSV downloads]** (and **[!Copy to Clipboard]**) from Analysis Workspace to remove formatting from exported data.
* Le séparateur des milliers ne sera plus inclu. (Le séparateur décimal sera toujours inclus et se conformera au format défini sous **[!UICONTROL Composants &gt; Paramètres de rapport &gt; Séparateur des milliers]**).
* Aucun symbole de devise n’est affiché.
* Aucun symbole de pourcentage n’est affiché.
* Les pourcentages sont en forme décimale; Par exemple, 75 % est représenté par 0,75.
* Le temps s’affiche en secondes.
* Les tableaux de cohortes affichent uniquement les valeurs brutes ; les pourcentages sont supprimés.
* Si un nombre n’est pas valide, une cellule vide s’affiche.

>[!NRemarque :]
>
> Les valeurs numériques qui utilisent une virgule comme séparateur décimal continueront à être citées dans le fichier CSV exporté.
