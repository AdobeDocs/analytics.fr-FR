---
description: Vous pouvez télécharger des projets enregistrés et non enregistrés au format PDF ou CSV.
title: Téléchargement de fichiers PDF ou CSV
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: ht
source-git-commit: 422b69a9f671bbd3c4e8f033916296cbdf7f27d9
workflow-type: ht
source-wordcount: '363'
ht-degree: 100%

---


# Téléchargement de fichiers PDF ou CSV

Vous pouvez télécharger des projets enregistrés et non enregistrés au format PDF ou CSV.

Le nom du fichier PDF ou CSV correspond au nom actuel du projet. Pour les projets non enregistrés, le fichier téléchargé comprend les modifications non enregistrées apportées au projet. Remarque : Vous ne pouvez pas planifier les projets non enregistrés au format PDF ou CSV.

N’oubliez pas ce qui suit :

* Les visualisations Abandons peuvent également être téléchargées au format CSV.
* Lorsque nous effectuons le rendu d’un projet au format PDF, seul le contenu de la page est rendu. Si un projet comprend des panneaux et des visualisations aux dimensions personnalisées, vous devez définir leurs dimensions automatiquement (à l’aide du bouton dans le coin supérieur droit) afin d’éviter toute troncation du contenu.
* L’exportation de fichiers PDF téléchargés dans le navigateur peut prendre plusieurs minutes. Ceci est dû au fait que nous devons exécuter à nouveau l’ensemble du projet sur nos serveurs avant d’effectuer le rendu au format PDF. Nous vous recommandons de ne pas quitter le projet tant que le fichier PDF n’a pas été téléchargé dans votre navigateur. Cependant, vous pouvez continuer à apporter des modifications au projet pendant que vous patientez.
* Nous sommes conscients que si vous avez des projets Workspace très longs, les fichiers PDF sont actuellement exportés sous la forme d’une page géante, plutôt que d’un document paginé. Nous travaillons à l’amélioration de l’exportation au format PDF de Workspace afin de permettre la pagination.

1. Créez ou ouvrez un projet.
1. Cliquez sur **[!UICONTROL Projet]** > **[!UICONTROL Télécharger CSV (ou Télécharger PDF).]**

Le 11 avril 2019, plusieurs modifications ont été apportées aux **[!UICONTROL téléchargements CSV]** (et à l’option **[!UICONTROL Copier vers le presse-papiers]**) depuis Analysis Workspace pour supprimer le formatage des données exportées.
* Le **[!UICONTROL séparateur des milliers]** n’est plus inclus. (Le séparateur décimal sera toujours inclus et se conformera au format défini sous **[!UICONTROL Composants > Paramètres de rapport > Séparateur des milliers]**).
* Aucun symbole de devise n’est affiché.
* Aucun symbole de pourcentage n’est affiché.
* Les pourcentages sont sous forme décimale. Par exemple, 75 % est représenté par 0,75.
* Le temps s’affiche en secondes.
* Les tableaux de cohortes affichent uniquement les valeurs brutes. Les pourcentages sont supprimés.
* Si un nombre n’est pas valide, une cellule vide s’affiche.
* Aucun arrondissement n’est appliqué (même s’il est spécifié dans la mesure calculée), les valeurs brutes sont indiquées.

>[!NRemarque] :
>
> les valeurs numériques qui utilisent une virgule comme séparateur décimal continuent à être placées entre guillemets dans le fichier CSV exporté.
