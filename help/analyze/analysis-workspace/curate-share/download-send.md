---
description: Vous pouvez télécharger des projets enregistrés et non enregistrés au format PDF ou CSV.
title: Téléchargement de fichiers PDF ou CSV
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: 422b69a9f671bbd3c4e8f033916296cbdf7f27d9
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 61%

---


# Téléchargement de fichiers PDF ou CSV

Vous pouvez télécharger des projets enregistrés et non enregistrés au format PDF ou CSV.

Le nom du fichier PDF ou CSV correspond au nom actuel du projet. Pour les projets non enregistrés, le fichier téléchargé comprend les modifications non enregistrées apportées au projet. Remarque : Vous ne pouvez pas planifier les projets non enregistrés au format PDF ou CSV.

N’oubliez pas ce qui suit :

* Les visualisations Abandons peuvent également être téléchargées au format CSV.
* Lorsque nous effectuons le rendu d’un projet au format PDF, seul le contenu de la page est rendu. Si un projet comprend des panneaux et des visualisations aux dimensions personnalisées, vous devez définir leurs dimensions automatiquement (à l’aide du bouton dans le coin supérieur droit) afin d’éviter toute troncation du contenu.
* L’exportation de fichiers PDF téléchargés dans le navigateur peut prendre plusieurs minutes. Ceci est dû au fait que nous devons réexécuter l’ensemble du projet sur nos serveurs avant de le rendre au format PDF. Nous vous recommandons de ne pas quitter le projet tant que le fichier PDF n’a pas été téléchargé dans votre navigateur. Cependant, vous pouvez continuer à apporter des modifications au projet pendant que vous attendez.
* Nous sommes conscients que si vous avez de très longs projets Workspace, les fichiers PDF sont actuellement exportés en tant que page géante plutôt qu’en tant que document paginé. Nous travaillons à une amélioration de l’exportation de Workspace PDF qui permettra la pagination.

1. Créez ou ouvrez un projet.
1. Cliquez sur **[!UICONTROL Projet]** > **[!UICONTROL Télécharger CSV (ou Télécharger PDF).]**

On April 11, 2019, several changes were made to **[!UICONTROL CSV downloads]** (and **[!UICONTROL Copy to Clipboard]**) from Analysis Workspace to remove formatting from exported data.
* The  **[!UICONTROL Thousands Separator]** is no longer included. (Le séparateur décimal sera toujours inclus et se conformera au format défini sous **[!UICONTROL Composants > Paramètres de rapport > Séparateur des milliers]**).
* Aucun symbole de devise n’est affiché.
* Aucun symbole de pourcentage n’est affiché.
* Les pourcentages sont sous forme décimale. Par exemple, 75 % est représenté par 0,75.
* Le temps s’affiche en secondes.
* Les tableaux de cohortes affichent uniquement les valeurs brutes. Les pourcentages sont supprimés.
* Si un nombre n’est pas valide, une cellule vide s’affiche.
* Aucun arrondi n’est appliqué (même s’il est spécifié dans la mesure calculée) - les valeurs brutes s’affichent.

>[!NRemarque] :
>
> les valeurs numériques qui utilisent une virgule comme séparateur décimal continuent à être placées entre guillemets dans le fichier CSV exporté.
