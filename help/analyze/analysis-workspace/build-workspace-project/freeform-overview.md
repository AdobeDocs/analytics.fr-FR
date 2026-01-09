---
description: Découvrez comment travailler avec des projets dans Analysis Workspace. Utilisez le gestionnaire de projets pour gérer les projets (créer, supprimer, déplacer, partager, approuver, épingler, copier et baliser).
keywords: Analysis Workspace
title: Vue d’ensemble des projets
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: f02b660b551f5291443b8f7c5c51179a06b22eb9
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

