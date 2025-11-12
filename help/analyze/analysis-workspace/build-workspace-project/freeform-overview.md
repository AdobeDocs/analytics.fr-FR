---
description: Découvrez comment travailler avec des projets dans Analysis Workspace. Utilisez le gestionnaire de projets pour gérer les projets (créer, supprimer, déplacer, partager, approuver, épingler, copier et baliser).
keywords: Analysis Workspace
title: Vue d’ensemble des projets
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '1680'
ht-degree: 91%

---

# Vue d’ensemble des projets

Les projets Workspace vous permettent de combiner des tableaux, des visualisations et des composants afin d’élaborer votre analyse et de la partager avec qui vous le souhaitez au sein de votre entreprise. Avant de démarrer votre premier projet, découvrez comment accéder à vos projets, les parcourir et les gérer.

Pour accéder aux projets dans Adobe Analytics, sélectionnez **[!UICONTROL Workspace]**.  Le gestionnaire **[!UICONTROL Projets]** répertorie tous les projets que vous possédez ou les projets partagés avec vous. Le Gestionnaire de projets avec la liste Projet est également la page de destination par défaut d’Adobe Analytics, sauf configuration contraire dans les Préférences.

![Page de destination du projet affichant la liste des projets.](assets/projects.png)


## Zone de titre

Dans la zone de titre ➊, vous pouvez créer un projet, créer un dossier, modifier vos préférences et afficher ou masquer un panneau avec des vignettes supplémentaires.

* Pour afficher ou masquer un panneau de gauche qui vous permet de choisir entre **[!UICONTROL Projets]** et **[!UICONTROL Formation]**, sélectionnez ![Rail](/help/assets/icons/Rail.svg).
* Le titre affiche les projets, éventuellement ajoutés avec un chemin d’accès au dossier que vous avez sélectionné. Par exemple, [!UICONTROL Projets] > **[!UICONTROL Dossier Entreprise]**. Vous pouvez sélectionner des parties de sous-dossier individuelles pour accéder directement au dossier spécifique.
* Pour afficher les vignettes d’un [**[!UICONTROL Projet vierge]**](create-projects.md), [**[!UICONTROL Carte de performance mobile vierge]**](/help/analyze/mobile-app/create-scorecard.md), **[!UICONTROL Ouvrez la documentation]** et **[!UICONTROL Ouvrir les notes de mise à jour]**, sélectionnez ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Afficher plus]**. Pour masquer la zone avec les tuiles, sélectionnez ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Afficher moins]**.
* En fonction de ce que vous sélectionnez pour l’affichage, à l’aide du [sélecteur Afficher](#show-selector), vous pouvez modifier les préférences et effectuer des actions sur le dossier actif visible dans **[!UICONTROL Projets]** :

  | Action | Description |
  |---|---|
  | **[!UICONTROL Créer un projet]** | Sélectionnez pour [créer un projet](create-projects.md). |
  | **[!UICONTROL Créer un dossier]** | Sélectionnez pour [créer un dossier](workspace-folders/create-folders.md). |
  | ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Modifier les préférences]** | [Modifiez les préférences](/help/analyze/analysis-workspace/user-preferences.md) pour tous vos projets. Lorsque le chemin de navigation se traduit par un espace limité, cette action fait partie du sous-menu ![Plus](/help/assets/icons/More.svg). |
  | **[!UICONTROL Ajouter des projets]** | Sélectionnez cette option pour [ajouter des projets](workspace-folders/add-projects.md) au dossier actif. Lorsque le chemin de navigation se traduit par un espace limité, cette action fait partie du sous-menu ![Plus](/help/assets/icons/More.svg). |
  | **[!UICONTROL Renommer le dossier]** | [Renomme](workspace-folders/manage-folders.md#rename-folders) le dossier actif. |
  | **[!UICONTROL Déplacer le dossier]** | [Déplace](workspace-folders/manage-folders.md#move-folders) le dossier actif. |
  | **[!UICONTROL Supprimer le dossier]** | [Supprime](workspace-folders/manage-folders.md#delete-folders) le dossier actif. |




## Liste de projets


La liste de projets ➋ affiche tous les projets que vous possédez et qui ont été partagés avec vous. La liste comporte les colonnes suivantes :

| Colonne | Description |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Lorsqu’un ou plusieurs projets sont sélectionnés, une barre d’actions bleue s’affiche au bas de l’interface Projet. Pour plus de détails, consultez [Actions](#actions). |
| ![Contour en forme d’étoile](/help/assets/icons/StarOutline.svg) | Sélectionnez ![Étoile](/help/assets/icons/Star.svg) pour mettre en favori ou ![StarOutline](/help/assets/icons/StarOutline.svg) pour retirer des favoris un projet. |
| **[!UICONTROL Titre et description]** | Pour modifier le projet, sélectionnez le lien du titre, qui ouvre le [projet Workspace](/help/analyze/analysis-workspace/home.md). Les projets partagés avec vous sont indiqués par ![Partager](/help/assets/icons/ShareAlt.svg). Sélectionnez ![InfoOutline](/help/assets/icons/InfoOutline.svg) pour afficher un menu contextuel contenant plus de détails sur le projet. Sélectionnez ![Plus](/help/assets/icons/More.svg) pour ouvrir un menu contextuel avec des actions. Pour plus de détails, consultez [Actions](#actions). |
| **[!UICONTROL Type]** | Un projet Workspace, un dossier ![FolderUser](/help/assets/icons/FolderUser.svg) ou une [Carte de performance mobile](/help/analyze/mobile-app/home.md). |
| **[!UICONTROL Étiquettes]** | Balises appliquées au projet. |
| **[!UICONTROL Planifié]** | Indique si un projet doit être envoyé par e-mail aux destinataires. Les options sont ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL On]** ou ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Off]**. Consultez [Envoyer des données de projet à d’autres personnes](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). |
| **[!UICONTROL Lien partagé (tout le monde)]** | Partager ou non un projet avec tout le monde, même avec des personnes qui n’ont pas accès à Analysis Workspace. Les options sont ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Actif]** ou ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Inactif]**. Consultez [Partager un projet avec tout le monde (aucune connexion requise)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required) dans [Partager des projets](/help/analyze/analysis-workspace/curate-share/share-projects.md) pour plus d’informations. |
| **[!UICONTROL Rôle de projet]** | Votre rôle pour le projet. Les options sont les suivantes : Modifier, Dupliquer et Afficher. Consultez [Rôles de projet](/help/analyze/analysis-workspace/curate-share/curate.md) pour plus d’informations. |
| **[!UICONTROL Suite de rapports]** | Suite de rapports à laquelle le projet est associé. |
| **[!UICONTROL Propriétaire]** | Personne qui a créé ce projet (vous ou quelqu’un qui a partagé le projet avec vous). |
| **[!UICONTROL Partagé avec]** | Utilisateurs et utilisatrices avec lesquels le projet a été partagé. |
| **[!UICONTROL Dernière modification]** | Date et heure de dernière modification du projet. |
| **[!UICONTROL Dernière ouverture]** | Date et heure de dernière ouverture du projet. |
| **[!UICONTROL ID du composant]** | L’identifiant du composant. |
| **[!UICONTROL Période la plus longue]** | Période la plus longue de l’un des panneaux ou de l’une des visualisations du projet. |
| **[!UICONTROL Nombre de requêtes]** | Nombre total de requêtes contenues dans le projet. |
| **[!UICONTROL Emplacement]** | Dossier dans lequel réside le projet. |

Pointez sur un en-tête de colonne pour afficher ![ChevronDown](/help/assets/icons/ChevronDown.svg) et sélectionnez dans le menu contextuel les options suivantes :

* **[!UICONTROL Tri ascendant]**
* **[!UICONTROL Tri descendant]**
* **[!UICONTROL Redimensionnez la colonne]**. Une ligne bleue s’affiche pour vous aider à redimensionner la colonne.

### Actions

Vous pouvez agir sur un ou plusieurs projets à l’aide du menu contextuel ![Plus](/help/assets/icons/More.svg) ou de la barre d’actions bleue.

| Icône | Action | Description |
|:---:| ---|---|
| ![CrossSize75](/help/assets/icons/Close.svg) | **[!UICONTROL *x *sélectionné]** | Désélectionnez les projets et dossiers sélectionnés et supprimez la barre d’actions bleue. |
| ![Supprimer](/help/assets/icons/Delete.svg) | **[!UICONTROL Supprimer]** | Supprimez un ou plusieurs projets ou dossiers. Il vous est demandé de confirmer. <p>Projets que vous supprimez :</p><ul><li>Impossible à récupérer</li><li>Suppression de la liste des projets</li><li>ne sont plus accessibles avec leur URL</li><li>ne figurent plus dans les diffusions planifiées (en cas de configuration précédente pour des diffusions planifiées)<br/>Pour plus d’informations sur les diffusions planifiées, voir la section [Projets planifiés](/help/components/scheduled-projects-manager.md).  </p> |
| ![Partager](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Partager]** | Partagez un projet. Consultez [Partager un projet](/help/analyze/analysis-workspace/curate-share/share-projects.md) pour plus d’informations. |
| ![Modifier](/help/assets/icons/Edit.svg) | **[!UICONTROL Renommer]** | Renommez un projet. Ouvre une **[!UICONTROL boîte de dialogue Renommer : *nom du projet *]**. Saisissez un nouveau nom et sélectionnez**[!UICONTROL Enregistrer ]**. |
| ![Copier](/help/assets/icons/Copy.svg) | **[!UICONTROL Copier]** | Copiez un ou plusieurs projets. Les projets reçoivent le même nom et le même suffixe `(Copy)`. |
| ![PinOnff](/help/assets/icons/PinOff.svg) | **[!UICONTROL Épingler]** ou **[!UICONTROL Détacher]** | Épinglez ou détacher un ou plusieurs projets ou dossiers. Les projets et dossiers épinglés apparaissent en haut de la liste et ignorent l’ordre de tri que vous spécifiez. |
| ![ArrowUp](/help/assets/icons/ArrowUp.svg) | **[!UICONTROL Déplacer vers le haut]** | Déplacez un projet ou un dossier épinglé vers le haut dans la liste des projets. |
| ![ArrowDown](/help/assets/icons/ArrowDown.svg) | **[!UICONTROL Déplacer vers le bas]** | Déplacez un projet ou un dossier épinglé vers le bas dans la liste des projets. |
| ![Libellé](/help/assets/icons/Label.svg) | **[!UICONTROL Étiquette]** | Balisez un ou plusieurs projets ou dossiers. La boîte de dialogue **[!UICONTROL Composants de balise]** s’affiche pour sélectionner une ou plusieurs balises. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les balises pour les projets ou dossiers sélectionnés. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Approuver]** ou **[!UICONTROL Annuler l’approbation]** | Approuver un projet ou en annuler l’approbation. Seuls les administrateurs et administratrices peuvent approuver les projets. |
| ![Fichier CSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exporter au format CSV]** | Exportez les projets sélectionnés dans un fichier CSV portant le nom `Project List.csv`. |
| ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) | **[!UICONTROL Ajouter des projets]** | Ajoutez un ou plusieurs projets à un dossier sélectionné. Dans **[!UICONTROL Ajouter des projets]**, vous pouvez sélectionner un ou plusieurs projets. Sélectionnez **[!UICONTROL Ajouter]** pour ajouter les projets au dossier. Consultez [Ajouter des projets à des dossiers](workspace-folders/add-projects.md#from-inside-a-folder) pour plus d’informations. |
| ![FolderAddTo](/help/assets/icons/FolderAddTo.svg) | **[!UICONTROL Déplacer vers]** | Déplacez un ou plusieurs projets sélectionnés vers un dossier. Dans **[!UICONTROL Sélectionner un dossier]**, sélectionnez le dossier dans lequel déplacer le projet sélectionné et sélectionnez **[!UICONTROL Déplacer]**. Consultez [Ajouter des projets à des dossiers](workspace-folders/add-projects.md#from-the-project-list) pour plus d’informations. |



## Sélecteur Afficher

Vous pouvez changer l’aspect de l’interface Projets à l’aide des sélecteurs **[!UICONTROL Afficher]** ➌. Le sélecteur **[!UICONTROL Afficher]** définit les options disponibles dans la [Zone de titre](#title-area) et les colonnes affichées dans la [Liste de projets](#project-list).

* Pour modifier les options disponibles pour la [Zone de titre](#title-area), sélectionnez **[!UICONTROL Afficher]** **[!UICONTROL Tous les projets]** ou **[!UICONTROL Afficher]** **[!UICONTROL Dossiers et projets]**.

* Pour définir les colonnes à afficher pour la [liste de projets](#project-list), sélectionnez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) et dans la boîte de dialogue **[!UICONTROL Personnaliser le tableau]**, sélectionnez ou désélectionnez les colonnes. Sélectionnez **[!UICONTROL Appliquer]** pour appliquer la personnalisation. Consultez [Liste de projets](#project-list) pour plus d’informations sur les colonnes.

## Panneau Filtrer

Vous pouvez filtrer les projets et les dossiers dans la [Liste des projets](#project-list) à l’aide du panneau Filtrer ➍. Pour afficher ou masquer le panneau Filtrer, utilisez ![Filtrer](/help/assets/icons/Filter.svg).

Le panneau Filtrer se compose des sections suivantes.

### Balises

| Balises | Description |
|---|---|
| ![Étiquettes](assets/projects-filters-tags.png){width="300"} | La section **[!UICONTROL Balises]** permet de filtrer par balise. <ul><li>Vous utilisez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des balises* pour rechercher les balises que vous souhaitez utiliser pour filtrer.</li><li>Vous pouvez sélectionnez plusieurs balises. Les balises disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtrer.</li><li>Les chiffres indiquent ce qui suit :<ul><li>**2︎⃣** : nombre de balises disponibles pour les projets résultant du filtre actuel.</li><li>7︎⃣ : nombre de projets associés à la balise spécifique.</li></ul></li></ul> |


### Suites de rapports

| Suites de rapports | Description |
|---|---|
| ![Suite de rapports](assets/projects-filters-reportsuites.png){width="300"} | La section **[!UICONTROL Suites de rapports]** permet de filtrer les suites de rapports. <ul><li>Utilisez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des suites de rapports* pour rechercher les suites de rapports que vous souhaitez utiliser pour filtrer.</li><li>Vous pouvez sélectionner plusieurs suites de rapports. Les suites de rapports disponibles dépendent des sélections effectuées dans d’autres sections du panneau de filtrage.</li><li>Les chiffres indiquent ce qui suit :<ul><li>**3︎⃣** : nombre de suites de rapports disponibles pour les projets résultant du filtre actuel.</li><li>4︎⃣ : nombre de projets associés à la suite de rapports spécifique.</li></ul></li></ul> |


### Propriétaires

| Propriétaire | Description |
|---|---|
| ![Propriétaires](assets/projects-filters-owners.png){width="300"} | La section **[!UICONTROL Propriétaire]** vous permet de filtrer les propriétaires. <ul><li>Utilisez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des propriétaires* pour rechercher les propriétaires que vous souhaitez utiliser pour filtrer.</li><li>Vous pouvez sélectionner plusieurs propriétaires. Les propriétaires disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtrer.</li><li>Les chiffres indiquent ce qui suit :<ul><li>**3︎⃣** : nombre de propriétaires disponibles pour les projets résultant du filtre actuel.</li><li>4︎⃣ : nombre de projets associés à la personne propriétaire spécifique.</li></ul></li></ul> |


### Type

| Type | Description |
|---|---|
| ![Type](assets/projects-filters-type.png){width="300"} | La section **[!UICONTROL Type]** permet de filtrer selon le type de projets ou de dossiers.<ul><li>Vous pouvez sélectionner l’une ou plusieurs des options suivantes :<ul><li> **[!UICONTROL Dossier]**</li><li>**[!UICONTROL Projet Espace de travail]**</li><li>**[!UICONTROL Carte de performance mobile]**</li></ul> <li>Vous pouvez sélectionner plusieurs filtres. Les autres filtres disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtrer.</li><li>Les chiffres indiquent ce qui suit :<ul><li>**5︎⃣** : nombre d’autres filtres disponibles pour les projets résultant du filtre actuel.</li><li>4︎⃣ : nombre de projets associés à l’autre filtre spécifique.</li></ul></li></ul> |


### Autres filtres

| Autres filtres | Description |
|---|---|
| ![Autres filtres](assets/projects-filters-others.png){width="300"} | La section **[!UICONTROL Autres filtres]** vous permet de filtrer selon un autre filtre prédéfini.<ul><li>Vous pouvez sélectionner l’une ou plusieurs des options suivantes :<ul><li> **[!UICONTROL Tout afficher]**</li><li>**[!UICONTROL Partagé avec moi]**</li><li>**[!UICONTROL À moi]**</li><li>**[!UICONTROL Approuvés]**</li><li>**[!UICONTROL Favoris]**</li></ul> Ce que vous pouvez sélectionner dépend de votre rôle et de vos autorisations.</li><li>Vous pouvez sélectionner plusieurs filtres. Les autres filtres disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtrer.</li><li>Les chiffres indiquent ce qui suit :<ul><li>**5︎⃣** : nombre d’autres filtres disponibles pour les projets résultant du filtre actuel.</li><li>4︎⃣ : nombre de projets associés à l’autre filtre spécifique.</li></ul></li></ul> |

## Recherche

Utilisez la zone de recherche ➎ pour rechercher des projets et des dossiers à l’aide du champ ![Rechercher](/help/assets/icons/Search.svg). Commencez la saisie et la [liste de projets](#project-list) filtre automatiquement selon votre entrée de recherche.

La zone de recherche affiche également les filtres appliqués à partir du panneau Filtrer.

* Pour supprimer un filtre, sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) dans le filtre.
* Pour supprimer tous les filtres, sélectionnez Effacer tout.

Si l’espace est limité pour l’affichage des filtres individuels, le message **[!UICONTROL Segmentation avec *x* filtres]** s’affiche.

* Pour supprimer un filtre, procédez comme suit :

   1. Utilisez **[!UICONTROL *x * filtres]**![ChevronDown](/help/assets/icons/ChevronDown.svg) pour ouvrir un menu contextuel répertoriant les types de filtres et les filtres individuels.
   1. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer un filtre.


<!--

# Projects overview

Workspace projects allow you to combine data components, tables and visualizations to craft your analysis and share with anyone in your organization. Before starting your first project, learn about how to access, navigate and manage your projects. 

Here is a video on how to build a Workspace project:


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Build a Workspace project](https://video.tv.adobe.com/v/334076?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


## Project list {#project-list}

When you first go to **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, the page lists all the projects you own or have been shared to you. This page is also the landing page for Adobe Analytics, unless you have previously set a custom landing page. 

The Projects page contains the following information: 

|  Element  | Description  |
|---|---|
| [Edit preferences](/help/analyze/analysis-workspace/user-preferences.md) | Manage settings for Analysis Workspace and its related components for all new projects or panels that you create.  |
| [Create folder](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)  | Add a new folder or subfolder to the list of projects and folders. |
| [Create project](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)  | Start a new project from scratch or from a report.  |
|  Show more  | This selection reveals options for creating a blank project or mobile scorecard, [viewing training tutorials](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction), or [viewing release notes](/help/release-notes/latest.md).  |
| ![Show filters](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) | To show or hide filters. You can filter on tags, report suite, owners, type (project, folder, mobile scorecard), and other filters. |
| ![Search](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | Use the search field to search for folders, Workspace projects or mobile scorecards. |
| Show Folders & Projects| Choose whether to show the folder structure of projects. For more information, see [About Folders in Analytics](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
|  ![Customize table](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) | This icon allows you to customize the columns you see for each project in the projects list.  |

The list of projects can display the following columns:

|  Column  | Description  |
|---|---|
| [!UICONTROL Name]  | Name of the Workspace project. Select ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) to show a popup with more details on a project or folder. Select ![More](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) to show actions available. See [Manage projects](#manage-projects) for more details.  |
| [!UICONTROL Type] | Indicates whether this entry is a Workspace project, a folder, or a [Mobile scorecard](/help/analyze/mobile-app/home.md). |
| [!UICONTROL Tags]  |Tags that were applied to the project.  |
| [!UICONTROL Scheduled] | Indicates whether projects are scheduled to be emailed to recipients. See [Schedule projects](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). |
| Shared link (anyone) | Projects can be shared with anyone, even with people who don't have access to Analysis Workspace. This column shows whether projects have been shared in this way. See [Share a project with anyone (no login required)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md) for more information. |
| [Project Role](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Indicates your role for the project - owners, edit, duplicate, view. |
| [!UICONTROL Report suite] | The report suite that the project is associated with. |
| [!UICONTROL Owner]  | The person who created this project (either you or someone who shared the project with you.)  |
| [!UICONTROL Shared with]  | Users that the project has been shared with.  |
| [!UICONTROL Last Modified]  | Date and time when the project was last modified.  |
| [!UICONTROL Last Opened]  | Date and time when the project was last opened.  |
| [!UICONTROL Last Used] | Date and time when the project was last used. |
| [!UICONTROL Project ID]  | The ID of the project.  |
| [!UICONTROL Longest Date Range]  | The longest date range of the project.  |
| [!UICONTROL Number of Queries]  | The total number of queries contained in the project.  |
| [!UICONTROL Location]  | The folder where the project resides.  |

### Manage projects

To manage projects, select one or more projects from the project list. 

From the blue action bar, you can select the following actions:

| Action | Description |
|---|---|
| ![Delete](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) Delete | When selected, a confirmation dialog prompts you to confirm the deletion of a Workspace project or Mobile scorecard. Select **[!UICONTROL OK]** to confirm. |
| ![Share](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg) Share | This action allows you to share your project. See [Share projects](../curate-share/share-projects.md).|
| ![Rename](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) Rename | Opens up a **[!UICONTROL Rename: *name*]** dialog to rename your project. Select **[!UICONTROL Save]** to save the new name for the project. |
| ![Copy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) Copy | Immediately copies the selected project to a new project with name *original name* (Copy).  |
| ![Pin](https://spectrum.adobe.com/static/icons/workflow_18/Smock_PinOff_18_N.svg) Pin | Immediately pins the project to the top of the list. Adds the ![Pin](https://spectrum.adobe.com/static/icons/workflow_18/Smock_PinOff_18_N.svg) indicator. |
| ![Tag](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Label_18_N.svg) Tag | Opens up the **[!UICONTROL Tag Project]** dialog. You can select an existing tag or add new tags. Select **[!UICONTROL Save]** to save the tags for the project. |
| ![(Un-)Approve](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CheckmarkCircle_18_N.svg) Approve or Unapprove |  Approves or unapproves the project.  |
| ![Export CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) Export CSV | Immediately downloads a file containing a comma-separated value list of the projects. |
| ![Move to](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FolderAddTo_18_N.svg) Move to | This action allows you to move the project to a folder. In the **[!UICONTROL Select Folder]** dialog, select a folder from the **[!UICONTROL Folder]** list, and select **[!UICONTROL Move]**. |


## Menu bar {#menu-bar}

Within a project, the menu provides options for managing your project, adding components, finding help, and more. You can also access each menu option by keyboard [shortcuts](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).


|  Menu item  | Description  |
|---|---|
|  Project  | This menu includes common actions for project management, including New, Open, Save, Save as, and [Save as company report](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md). You can also refresh the entire project to retrieve the most recent data and definitions by clicking Refresh Project. [Download CSV and PDF](/help/analyze/analysis-workspace/curate-share/download-send.md) options enable you to export data from Workspace. [Project Info & Settings](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) offers many options for managing your project.  |
|  Edit  | Undo or redo your last action. Clear All resets your project to a blank starting point. |
|  Insert  | Insert new panels or visualizations from this menu. You can also insert new panels and visualizations from the left rail.  |
|  [Components](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)  | Create new segment, calculated metric, date range, or alert components from your project. You can also create new components from the left rail. If your component definitions have recently changed, Refresh Components retrieves the latest definitions. |
|  [Share](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md)  | Curate, share and schedule PDF/CSV projects to recipients in your organization.  |
|  Help  | Access help documentation, videos, and the Analytics [Experience League community](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community). Manage the visibility of Workspace tips as well as the [debugger](https://developer.adobe.com/analytics-apis/docs/2.0/). Find details about Workspace and factors that impact project [performance](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md).  |
|  Share button or Owner  | If you are in an Own or Edit for the project, the Share button in the top-right gives you one-click access to manage your project recipients. If you are in a Duplicate or View role for the project, you see the project owner's name. |

### Project Info & Settings {#info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="Count repeat instances"
>abstract="Specifies whether repeat instances are counted in reports.<br/><br/>Note: this setting does not apply to Flow or Fallout visualizations."

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="Count repeat instances"
>abstract="Specifies whether repeat instances are counted in reports.<br/>Note: this setting does not apply to Flow or Fallout visualizations."


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="Allow commenting"
>abstract="When enabled, a comments area is available in the right rail of the project in Analysis Workspace."



**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & settings]** provides project-level information on the currently active project.

![Project Info](assets/projectinfo.png)

Settings include:

|  Setting  | Description  |
|---|---|
|  Project Name  | The name given to the project. You can double-click the name to edit it.  |
|  Owner  | Project owner name  |
|  Last Modified  | Date of last modification to the project.  |
|  Tags  |Lists any tags applied to a project for easier categorization.  |
|  Description  | A description is useful for clarifying the purpose of a project. You can double-click the description to edit it.  |
|  Count repeat instances  | Specifies whether repeat instances are counted in reports. For example, this setting (when activated) treats multiple consecutive pages views to the same page as multiple page views. With it off, they count as a single page view (this setting only affects certain metrics, such as Single Page Visits). **Note**: This setting does not apply to Flow or Fallout visualizations.  |
| [Show annotations](/help/analyze/analysis-workspace/components/annotations/overview.md) | Specify whether to show annotations in the project or not. |
|  [Project color palette](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md)  | You can change the categorical color palette used in Workspace, by choosing from out-of-the-box palettes that have been optimized for color blindness, or by specifying your custom palette. This feature affects many things in Workspace, including most visualizations.  |
| [View Density](/help/analyze/analysis-workspace/build-workspace-project/view-density.md) | Lets you see more data on the screen by reducing the vertical padding of the left rail, freeform tables and cohort tables. |

## Left rail {#left-rail}

Within a project, various icons are available in the left rail, and each represents important tools to build your project:

| Icon | Functionality |
|---|---|
| ![panels icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg) | [Panels](/help/analyze/analysis-workspace/c-panels/panels.md) |
| ![visualizations icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphBarVertical_18_N.svg) |[Visualizations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) |
| ![components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) | [Components](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) |
| ![data dictionary icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Bookmark_18_N.svg) | [Data dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) |
| ![toc icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ViewList_18_N.svg) | [Table of contents](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md) |

Components (dimensions, metrics, segments, date ranges) in the left rail relate to the active panel data view. A blue border identifies the active panel, and the active report suite is listed at the top of the component rail.


## Right-click menu

Here is a video on using the right-click menu in Analysis Workspace:


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Using the context menu](https://video.tv.adobe.com/v/23981?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

## Project canvas {#canvas}

The project canvas is where you bring together panels, tables, visualizations, and components to build your analysis. A project can contain many panels, and each panel can contain many tables and visualizations.

Panels are helpful when you want to organize your projects according to time periods, report suites, or analysis use case. The active panel has a colored border around it, and determines what components are available in the left rail.

Depending on the starting point you chose for your projects, you either have a [freeform table](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) or a [blank panel](/help/analyze/analysis-workspace/c-panels/blank-panel.md) in the canvas to begin with. The quickest way to start analyzing is to select one or many components and simply drag & drop them into the project canvas. A table of data is rendered automatically for you. [Learn more](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) about the different options for building a table, or leverage the available [training tutorial](/help/analyze/analysis-workspace/home.md) for more guidance on building your first project.

![](assets/canvas.png)

-->