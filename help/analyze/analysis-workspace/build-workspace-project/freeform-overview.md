---
description: valeur nulle
keywords: Analysis Workspace
title: Aperçu de la création d’un projet
topic: Reports and analytics
uuid: a68be05d-f31e-4e6d-ad04-c784ecb0eb00
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Aperçu de la création d’un projet

**[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**

Créez un projet Analytics durable quelle que soit la combinaison de visualisations, de composants de rapports et de tableaux de données. Cet environnement reprend nombre des fonctions du créateur de tableaux d’Ad Hoc Analysis dans Analytics.

Dans Analysis Workspace, comparez et disséquez les données de façons inédites. Par exemple, configurez des rapports de classement et apportez des modifications itératives immédiates à la requête de données, puis accédez et manipulez les valeurs au niveau de la création de rapports.

La requête parvient directement au moteur de production de rapports. Vous pouvez apporter des modifications en ligne sans solliciter d’autres rapports pour créer votre analyse. Les résultats sont renvoyés immédiatement, sans que le navigateur soit actualisé.

## Page de liste de projets de l’Workspace  {#section_39AA007D7C384F4E869F842F1C7B11F8}

When you first go to **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, the page lists all the projects you own or have been granted access to. You can set this page to be your Adobe Analytics landing page by clicking **[!UICONTROL Set as Landing Page]**. (Si cette option n’est pas visible, comme dans l’illustration ci-après, cette page est déjà définie comme page d’entrée.)

![](assets/sample-project.png)

La page de liste de projets de l’Workspace présente les informations suivantes :

| Élément | Description |
|---|---|
| Projet  [Modèles](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) | Utilisez ces modèles de projet prérenseignés tels quels ou adaptez-les en fonction de vos besoins (en ajoutant ou en remplaçant des mesures ou des visualisations, par exemple) et enregistrez-les sous un nouveau nom. |
| [Créer un projet](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md) | Cliquez sur ce lien pour démarrer un projet entièrement nouveau. |
| Gérer les projets | Clicking this link takes you to the Projects Component Manager ( **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Projects]**), which lists all your projects and lets you tag, share, delete, rename, approve, copy, and export projects to CSV. |
| Afficher les tutoriels | Permet d’accéder aux [vidéos YouTube Analysis Workspace](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS). |
| Nom | Nom du projet de l’Workspace. |
| Créé par | Personne qui a créé ce projet (vous ou quelqu’un qui a partagé le projet avec vous). |
| Balises | Tags that were applied to the project, either in the Projects Component Manager or under **[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**. |
| Dernière modification | Date et heure de dernière modification du projet. |

## Informations et paramètres du projet {#section_63773D0B9E4543E88068ECECB9EEB4C6}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**

![](assets/projectinfo.png)

**[!UICONTROL Project Info & Settings]** fournit des informations au niveau du projet sur le projet actuellement actif.

| Paramètre | Description |
|---|---|
| Nom du projet | Nom donné au projet. Double-cliquez dessus pour le modifier. |
| Créé par | Nom du titulaire du projet. |
| Dernière modification | Date de la dernière modification du projet. |
| Balises | Répertorie les balises appliquées à un projet afin de faciliter la catégorisation. Vous pouvez également baliser les projets tout en les enregistrant. View a project&#39;s tags on the Workspace Landing Page in the [!UICONTROL Tags] column. |
| Description | Une description est utile pour clarifier l’objet d’un projet. Double-cliquez dessus pour la modifier. |
| Compter les instances répétées | Ce paramètre indique si les instances répétées sont comptabilisées dans les rapports. S’il existe plusieurs valeurs consécutives pour la même variable, vous pouvez les comptabiliser comme une seule instance ou comme plusieurs instances de la variable. |
| Modèle de couleurs de visualisation | Vous pouvez modifier le modèle de couleurs utilisé dans Workspace en choisissant une autre palette de couleurs ou en spécifiant votre propre palette. Cette fonction affecte de nombreux éléments dans Workspace, y compris la plupart des visualisations. |
| Densité d’affichage | Permet de voir plus de données sur l’écran en réduisant l’espacement vertical du rail gauche, dans les tableaux à structure libre et dans les tableaux de cohortes. |

## Menu Projets {#section_850CDFCB86A64EB0A0AD5B9E0FCB7013}

Le menu Projets supérieur ressemble à ce qui suit :

![](assets/new-project-menus.png)

Les sous-menus contiennent les options suivantes.

>[!NOTE] Les options marquées d’un astérisque (*) s’affichent uniquement avec les projets **enregistrés**.

| Projet | Modifier | Insérer | Composants | Partager | Aide |
|---|---|---|---|---|---|
| Nouveau | Annuler | Nouveau panneau | Nouveau segment | Partager le projet | Vidéos |
| Ouvrir | Effacer | Nouveau panneau à structure libre | Nouvelle mesure | Obtenir le lien du projet* | Touches de raccourci |
| Enregistrer | Effacer tout | Nouveau panneau de comparaison des segments | Nouvelle période | Envoyer le fichier maintenant* | Forum d’aide |
| Enregistrer sous* |  | Nouveau tableau à structure libre | Nouvelle alerte | Envoyer le fichier selon le calendrier* |  |
| Définir comme page d’entrée* |  | Nouvelle ligne | Actualiser les composants | Traiter les données du projet |  |
| Actualiser le projet |  | Nouvelle barre |  |  |  |
| Télécharger CSV |  |  |  |  |  |
| Télécharger un PDF* |  |  |  |  |  |
| Informations et paramètres du projet |  |  |  |  |  |

## Rail de gauche  {#section_271295C26EC840ABB2A8E7EC0498B60E}

Le rail de gauche comprend trois icônes, qui permettent d’accéder aux panneaux, aux [visualisations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) et aux [composants](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) (dimensions, mesures, segments, périodes) en un seul clic :

![](assets/panels.png) ![](assets/visualizations.png) ![](assets/components.png)

A **[!UICONTROL Blank Panel]** was added to the list of panels accessible from the left rail. Pour créer un **panneau de cohortes**, faites glisser un panneau vierge dans une visualisation Tableau de cohortes.
