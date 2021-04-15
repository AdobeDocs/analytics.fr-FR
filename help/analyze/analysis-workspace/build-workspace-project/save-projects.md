---
description: Découvrez les différentes options d’enregistrement, notamment l’enregistrement automatique, Enregistrer sous et l’enregistrement en tant que modèle.
title: Enregistrement des projets
feature: Concepts de base de Workspace
role: Business Practitioner, Administrator
exl-id: e8206956-6e24-4a3a-8c3f-8acf1fb9d800
translation-type: tm+mt
source-git-commit: b6bf9e97c2eada3b9510d50c4c9196d7b09b5a65
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 70%

---

# Enregistrement des projets

Pour enregistrer vos modifications dans un projet, accédez au menu **[!UICONTROL Projet]** de Workspace. En outre, Adobe enregistre automatiquement les projets dans certains cas.

## Options d’enregistrement des projets {#Save}

Il existe différentes actions d’enregistrement que vous pouvez effectuer sous le menu **[!UICONTROL Projet]**, selon la manière dont vous souhaitez accéder à votre analyse à l’avenir.

| Action | Description |
|---|---| 
| **[!UICONTROL Enregistrer]** | Enregistrez les modifications apportées au projet. Si le projet est partagé, les destinataires du projet verront également les modifications. Lorsque vous enregistrez le projet pour la première fois, vous êtes invité à lui attribuer un nom, une description (facultative) et à ajouter des balises (facultatives). |
| **[!UICONTROL Enregistrer avec les notes]** | Avant l’enregistrement de votre projet, ajoutez des remarques sur les modifications apportées au projet. Les notes seront stockées avec la version du projet et sont disponibles pour tous les éditeurs sous Project > Open previous version. |
| **[!UICONTROL Enregistrer sous]** | Créez un doublon du projet. Le projet d’origine ne sera pas affecté. |
| **[!UICONTROL Enregistrer en tant que modèle]** | Enregistrez votre projet comme [modèle personnalisé](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html) disponible pour votre entreprise sous **[!UICONTROL Projet > Nouveau]** |

![](assets/save-project.png)

## Enregistrement automatique {#Autosave}

Les projets existants, c’est-à-dire les projets enregistrés au moins une fois auparavant, sont automatiquement enregistrés toutes les deux minutes sur votre ordinateur local. Les nouveaux projets qui n’ont jamais été enregistrés ne sont pas enregistrés automatiquement.

Plusieurs scénarios permettent d’éviter les modifications non enregistrées d’un projet. Différentes actions s’offrent alors à vous.

### Ouverture d’un autre projet Workspace

Adobe permet d’enregistrer avant de quitter la page. Après avoir quitté un projet existant, la copie locale enregistrée automatiquement est supprimée.

![](assets/existing-save.png)

### Quitter ou fermer un onglet

Le navigateur signale que les modifications non enregistrées seront perdues. Vous pouvez choisir de quitter ou d’annuler.

![](assets/browser-image.png)

### Blocage du navigateur ou expiration d’une session

Pour les projets **existants**, lorsque l’utilisateur revient à Workspace, une fenêtre modale de **récupération du projet** s’affiche. Sélectionnez « Oui » pour restaurer le projet à partir de la copie locale enregistrée automatiquement. Sélectionnez « Non » pour supprimer la copie locale enregistrée automatiquement et ouvrir la dernière version du projet enregistrée par l’utilisateur.

![](assets/project-recovery.png)

Pour les **nouveaux** projets qui n’ont jamais été enregistrés, les modifications non enregistrées ne sont pas récupérables.

## Ouvrir la version précédente {#previous-version}

Pour ouvrir une version précédente d&#39;un projet :

1. Accéder à Projet > Ouvrir la version précédente
1. Examinez la liste des versions antérieures disponibles. Horodatage et éditeur sont fournis, en plus des notes si elles ont été ajoutées lors de l’enregistrement de l’éditeur. Les versions sans notes sont stockées pendant 90 jours ; les versions contenant des notes sont conservées pendant 1 an.
1. Sélectionnez une version précédente et cliquez sur Charger.
1. La version précédente se charge avec une notification. La version précédente ne deviendra pas la version enregistrée actuelle de votre projet tant que vous n&#39;aurez pas cliqué sur Enregistrer. Si vous quittez la version chargée, lorsque vous revenez, vous verrez la dernière version enregistrée du projet.
