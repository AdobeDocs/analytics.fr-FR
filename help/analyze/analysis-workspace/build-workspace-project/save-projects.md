---
description: Découvrez les différentes options d’enregistrement, notamment l’enregistrement automatique, l’enregistrement sous, l’enregistrement en tant que modèle et ouvrez les versions précédentes.
title: Enregistrement des projets
feature: Workspace Basics
role: User, Admin
exl-id: e8206956-6e24-4a3a-8c3f-8acf1fb9d800
source-git-commit: 598271d12257df2f78128e44ea04f04db8fde811
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 39%

---

# Enregistrement des projets

Les projets dans Analysis Workspace sont automatiquement enregistrés toutes les 2 minutes.

Vous pouvez également enregistrer manuellement des projets. D’autres options, telles que l’ajout de balises ou de notes, sont disponibles lorsque vous enregistrez un projet manuellement.

## Enregistrement manuel de projets {#Save}

Plusieurs options sont disponibles lors de l’enregistrement manuel d’un projet dans Analysis Workspace.

Pour enregistrer manuellement un projet :

1. Une fois votre projet ouvert dans Analysis Workspace, sélectionnez **[!UICONTROL Projet]**, puis choisissez l’une des options suivantes :

   | Action | Description |
   |---|---| 
   | **[!UICONTROL Enregistrer]** | Enregistrez les modifications apportées au projet. Si le projet est partagé, les destinataires du projet verront également les modifications. Lorsque vous enregistrez le projet pour la première fois, vous êtes invité à lui attribuer un nom, une description (facultative) et à ajouter des balises (facultatives). |
   | **[!UICONTROL Enregistrer avec les notes]** | Avant l’enregistrement de votre projet, ajoutez des notes sur les modifications apportées au projet. Les notes sont stockées avec la version du projet et sont disponibles pour tous les éditeurs sous [!UICONTROL Projet] > [!UICONTROL Ouvrir la version précédente]. |
   | **[!UICONTROL Enregistrer sous]** | Créez un doublon du projet. Le projet d’origine ne sera pas affecté. |
   | **[!UICONTROL Enregistrer en tant que modèle]** | Enregistrez votre projet comme [modèle personnalisé](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=fr) disponible pour votre entreprise sous **[!UICONTROL Projet > Nouveau]** |

   ![](assets/save-project.png)

## Enregistrement automatique {#Autosave}

Tous les projets dans Analysis Workspace sont automatiquement enregistrés toutes les 2 minutes sur votre ordinateur local. Cela inclut les nouveaux projets qui ne sont pas encore enregistrés manuellement.

* **Nouveaux projets :** Même si de nouveaux projets sont enregistrés automatiquement, vous devez enregistrer chaque nouveau projet manuellement la première fois. Analysis Workspace vous invite à enregistrer les nouveaux projets manuellement lorsque vous passez à un autre projet, lorsque vous fermez l’onglet du navigateur, etc.

   Si, pour une raison quelconque, vous perdez inopinément l’accès à un nouveau projet avant de l’enregistrer manuellement, une version de récupération de votre projet est enregistrée sur la page d’entrée Analysis Workspace dans un dossier appelé `Recovered Projects (Last 7 Days)`. Vous devez restaurer le projet récupéré et l’enregistrer manuellement à l’emplacement souhaité.

   Pour restaurer un projet récupéré :

   1. Accédez au [!UICONTROL **Projets récupérés**] sur la landing page Analysis Workspace.

      ![](assets/recovered-folder.png)

   1. Ouvrez votre projet et enregistrez-le à l’emplacement souhaité.

* **Projets existants :** Si, pour une raison quelconque, vous quittez un projet avec des modifications qui ne sont pas encore enregistrées automatiquement, Analysis Workspace vous invite à enregistrer vos modifications ou fournit un message d’avertissement.

   Voici quelques scénarios courants :

### Ouvrir un autre projet

Si vous ouvrez un projet supplémentaire alors que vous travaillez sur un projet qui contient des modifications qui ne sont pas encore enregistrées automatiquement, Analysis Workspace vous invite à enregistrer le projet actif avant de le quitter.

Les options disponibles sont les suivantes :

* **Enregistrer :** Remplace la copie locale enregistrée automatiquement la plus récente de votre projet par vos dernières modifications.
* **Enregistrer sous :** Enregistre vos dernières modifications en tant que nouveau projet. Le projet d’origine n’est enregistré qu’avec les modifications enregistrées automatiquement les plus récentes.
* **Ignorer les modifications :** Ignore vos dernières modifications. Le projet conserve les modifications enregistrées automatiquement les plus récentes.

![](assets/existing-save.png)

### Quitter ou fermer un onglet

Si vous quittez la page ou fermez l’onglet du navigateur lors de l’affichage d’un projet avec des modifications qui ne sont pas encore automatiquement enregistrées, le navigateur vous avertit que vos modifications non enregistrées seront perdues. Vous pouvez choisir de quitter ou d’annuler.

![](assets/browser-image.png)

### Blocage du navigateur ou expiration d’une session

Si votre navigateur se bloque ou si votre session expire, la prochaine fois que vous accédez à Analysis Workspace, vous êtes invité à récupérer toutes les modifications apportées à votre projet qui ne sont pas encore enregistrées automatiquement.

Vous trouverez ci-dessous la boîte de dialogue Récupération de projet qui s’affiche la première fois que vous accédez à Analysis Workspace après un blocage ou un délai d’expiration.

Sélectionner **Oui** pour restaurer le projet à partir de la copie enregistrée automatiquement la plus récente.

Sélectionner **Non** pour supprimer la copie enregistrée automatiquement et ouvrir la dernière version enregistrée par l’utilisateur du projet.

![](assets/project-recovery.png)

Pour les **nouveaux** projets qui n’ont jamais été enregistrés, les modifications non enregistrées ne sont pas récupérables.

## Ouvrir une version précédente {#previous-version}

>[!NOTE]
>
>Les versions précédentes du projet sont actuellement en version limitée.

Pour ouvrir une version précédente d’un projet :

1. Accédez à **[!UICONTROL Projet]** > **[!UICONTROL Ouvrir la version précédente]**

   ![](assets/previous-versions.png)

1. Consultez la liste des versions antérieures disponibles.
   [!UICONTROL Date et heure] et [!UICONTROL Éditeur] s’affichent, en plus des [!UICONTROL Notes] s’ils ont été ajoutés lorsque l’[!UICONTROL Éditeur] a été enregistré. Les versions sans notes sont stockées pendant 90 jours. Les versions avec notes sont stockées pendant 1 an.
1. Sélectionnez une version précédente et cliquez sur **[!UICONTROL Charger]**.
La version précédente se charge ensuite avec une notification. La version précédente ne devient pas la version enregistrée actuelle de votre projet tant que vous n’avez pas cliqué sur **[!UICONTROL Enregistrer]**. Si vous quittez la version chargée, lorsque vous revenez, la dernière version enregistrée du projet s’affiche.
