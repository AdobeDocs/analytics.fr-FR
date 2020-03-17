---
description: Vous pouvez télécharger des projets enregistrés et non enregistrés au format PDF ou CSV.
title: Téléchargement de fichiers PDF ou CSV
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: 08d564f7fb06b94c2010515ea4a1dcbb2e6e2815

---


# Téléchargement de fichiers PDF ou CSV

Vous pouvez télécharger des projets enregistrés et non enregistrés au format PDF ou CSV.

Le nom du fichier PDF ou CSV correspond au nom actuel du projet. Pour les projets non enregistrés, le fichier téléchargé comprend les modifications non enregistrées apportées au projet. Remarque : Vous ne pouvez pas planifier les projets non enregistrés au format PDF ou CSV.

N’oubliez pas ce qui suit :

* Les visualisations Abandons peuvent également être téléchargées au format CSV.
* Lorsque nous effectuons le rendu d’un projet au format PDF, seul le contenu de la page est rendu. Si un projet comprend des panneaux et des visualisations aux dimensions personnalisées, vous devez définir leurs dimensions automatiquement (à l’aide du bouton dans le coin supérieur droit) afin d’éviter toute troncation du contenu.
* L’exportation des fichiers PDF téléchargés dans le navigateur peut prendre plusieurs minutes. Ceci est dû au fait que nous devons réexécuter l’ensemble du projet sur nos serveurs avant de le rendre au format PDF. Nous vous recommandons de ne pas quitter le projet tant que le fichier PDF n’est pas téléchargé dans votre navigateur. Toutefois, vous pouvez continuer à apporter des modifications au projet pendant l’attente.
* Nous savons que si vous avez de très longs projets Workspace, les fichiers PDF sont actuellement exportés sous forme d’une page géante plutôt que d’un  paginé. Nous travaillons à une amélioration de l’exportation de PDF Workspace qui permettra la pagination.

1. Créez ou ouvrez un projet.
1. Cliquez sur **[!UICONTROL Project]** > **[!UICONTROL Download CSV (or Download PDF).]**

Le 11 avril 2019, plusieurs modifications ont été apportées aux **[!CSV téléchargements]** (et **[!Ccopies dans le Presse-papiers]**) depuis Analysis Workspace pour supprimer le formatage des données exportées.
* Le séparateur des milliers ne sera plus inclus. (The decimal separator will continue to be included, and will adhere to the format defined under **[!UICONTROL Components > Report Settings > Thousands Separator]**).
* Aucun symbole de devise n’est affiché.
* Aucun symbole de pourcentage n’est affiché.
* Les pourcentages sont sous forme décimale. Par exemple, 75 % est représenté par 0,75.
* Le temps s’affiche en secondes.
* Les tableaux de cohortes affichent uniquement les valeurs brutes. Les pourcentages sont supprimés.
* Si un nombre n’est pas valide, une cellule vide s’affiche.

>[!NRemarque] :
>
> les valeurs numériques qui utilisent une virgule comme séparateur décimal continuent à être placées entre guillemets dans le fichier CSV exporté.
