---
description: Vous pouvez télécharger des projets enregistrés et non enregistrés au format PDF ou CSV.
seo-description: Vous pouvez télécharger des projets enregistrés et non enregistrés au format PDF ou CSV.
seo-title: Téléchargement de fichiers PDF ou CSV
title: Téléchargement de fichiers PDF ou CSV
uuid: 8 af 5 f 3 d 7-5870-4 ed 6-8 a 9 f-ef 290 a 48 ef 5 f
translation-type: tm+mt
source-git-commit: b9e57162fae605719d7d85aad52a29165cb63fe4

---


# Téléchargement de fichiers PDF ou CSV

Vous pouvez télécharger des projets enregistrés et non enregistrés au format PDF ou CSV.

Le nom du fichier PDF ou CSV correspond au nom actuel du projet. Pour les projets non enregistrés, le fichier téléchargé comprend les modifications non enregistrées apportées au projet. Remarque : Vous ne pouvez pas planifier les projets non enregistrés au format PDF ou CSV.

>[!NOTE]
>
>Nous prenons également en charge la visualisation Abandons au format CSV.

>[!NOTE]
>
>Lors de la génération d'un projet au format PDF, nous venons de générer ce qui se trouve sur la page. Si un projet comprend des panneaux et des visualisations aux dimensions personnalisées, vous devez définir leurs dimensions automatiquement (à l’aide du bouton dans le coin supérieur droit) afin d’éviter toute troncation du contenu.

1. Créez ou ouvrez un projet.
1. Click **[!UICONTROL Project]** &gt; **[!UICONTROL Download CSV (or Download PDF).]**

On April 11, 2019, several changes were made to **[!CSV downloads]** (and **[!Copy to Clipboard]**) from Analysis Workspace to remove formatting from exported data.
* Le séparateur des milliers ne sera plus inclu. (Le séparateur décimal sera toujours inclus et se conformera au format défini sous **[!UICONTROL Composants &gt; Paramètres de rapport &gt; Séparateur des milliers]**).
* Aucun symbole de devise n'est affiché.
* Aucun symbole de pourcentage n'est affiché.
* Les pourcentages sont au format décimal ; Par exemple, 75 % est représenté comme 0,75.
* La durée est indiquée en secondes.
* Les tableaux de cohortes affichent uniquement les valeurs brutes ; les pourcentages sont supprimés.
* Si un nombre n'est pas valide, une cellule vide s'affiche.

>[!Note :]
>
> Les valeurs numériques qui utilisent une virgule comme séparateur décimal continueront à être citées dans le fichier CSV exporté.