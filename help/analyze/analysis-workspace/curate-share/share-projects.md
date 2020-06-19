---
description: Partage de projets et rôles de projets dans Workspace
keywords: Analysis Workspace sharing
title: Projets Share Workspace
translation-type: tm+mt
source-git-commit: 17c963fa6a0fc24d2e3ab45500922ea17ad42240
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 9%

---


# Projets Share Workspace

Le partage met un projet à la disposition d’autres utilisateurs Analysis Workspace de votre entreprise. Les [traitements](curate.md) appliqués sont répercutés lorsque les destinataires ouvrent le projet.

## Rôles de projet

Vous pouvez ajouter des destinataires à l’un des trois rôles de projet. Les rôles de projet sont liés à l’utilisateur et à un ID de projet spécifique. Les rôles de projet sont indépendants des autorisations d’utilisateur gérées dans la console [d’administration](https://docs.adobe.com/content/help/fr-FR/core-services/interface/manage-users-and-products/admin-getting-started.html)Experience Cloud.

| Rôle | Contrôle du projet |
|---|---|
| Peut modifier | Les destinataires peuvent Enregistrer les modifications dans un projet et agir en tant que copropriétaires.<br>Ce rôle est utile si vous souhaitez collaborer avec des collègues sur un projet. |
| Peut dupliquer | Les destinataires peuvent Enregistrer sous et ont accès au rail de gauche. Les interactions ne sont pas limitées.<br>Ce rôle est utile si vous souhaitez partager un projet avec des utilisateurs qui comprennent les données de votre entreprise et comment utiliser l’Analysis Workspace, mais que vous ne souhaitez pas que votre projet enregistré soit modifié. |
| Peut afficher | Les Destinataires ne peuvent pas enregistrer sous et n’ont pas accès au rail de gauche. Les interactions sont également limitées.<br>Ce rôle est utile si vous souhaitez partager un projet avec des utilisateurs qui connaissent moins bien la structure de données de votre entreprise, Analysis Workspace ou Adobe Analytics en général. Cependant, vous souhaitez toujours qu’ils consomment des données et des informations dans un environnement sûr.<br>En savoir plus sur l’expérience [du projet](/help/analyze/analysis-workspace/curate-share/view-only-projects.md)Can vue. |

>[!IMPORTANT]
> Les destinataires de projet ajoutés avant le 18 juin 2020 ont été migrés dans un rôle de projet. Les utilisateurs administrateurs ont effectué la migration vers le rôle **[!UICONTROL Can edit]** et les utilisateurs non administrateurs ont effectué la migration vers le rôle de duplicata **** Can. Ces rôles offrent la même expérience de projet qu&#39;auparavant. En outre, tous les groupes (y compris &quot;Tous&quot;) ont migré vers le rôle duplicata **** Can.

### Aucun rôle affecté

Si un destinataire n’est pas affecté à un rôle et reçoit un lien vers le projet (**[!UICONTROL Partager]>[!UICONTROL Obtenir le lien]** du projet), il sera placé par défaut dans le rôle de vue **** Can.

### Plusieurs rôles attribués

Si un destinataire est placé dans plusieurs rôles, il obtient toujours le meilleur contrôle. Cela peut se produire si un utilisateur est ajouté à la fois en tant qu’individu et dans le cadre d’un groupe. Par exemple, si l’utilisateur 1 est autorisé à modifier et **[!UICONTROL peut vue]** rôles, il aura **[!UICONTROL peut modifier]** le contrôle du projet.

### Administrateurs et rôles

Les administrateurs placés dans un duplicata **** Can ou une vue **** Can recevront ces expériences limitées lorsqu’ils ouvriront un projet. Si vous le souhaitez, un administrateur peut augmenter son rôle pour **[!UICONTROL pouvoir modifier]** à tout moment via **[!UICONTROL Composants]>[!UICONTROL Projets]**.

## Ajouter les destinataires au projet partagé

Pour ajouter des destinataires à votre projet partagé :

1. Cliquez sur **[!UICONTROL Partager]** > **[!UICONTROL Partager le projet]**.
S&#39;il y a des modifications non enregistrées, vous serez invité à enregistrer d&#39;abord votre projet.
1. Ajoutez des destinataires ou des groupes d’utilisateurs.
Pour obtenir la description de chaque rôle, reportez-vous à l’icône d’aide en haut de l’écran.
1. (Facultatif) Partagez des composants de projet incorporés (segments, mesures calculées et plages de dates) avec tous les destinataires.
Une fois partagés, ces composants s’affichent dans la liste déroulante Composants de l’espace de travail du destinataire. Notez que ce paramètre n’est pas conservé. Il s’agit d’une action unique au moment du partage.
1. (Facultatif) Définissez cette page comme landing page pour les destinataires.
Ce paramètre est ponctuel ; c’est une action unique au moment du partage.
1. Cliquez sur Partager.
Vous pouvez également cliquer sur **[!UICONTROL Traiter et Partager]** pour appliquer automatiquement la gestion du projet. Si un projet a déjà été partagé, ces boutons indiqueront **[!UICONTROL Mettre à jour]** et **[!UICONTROL Traiter et mettre à jour]**. En savoir plus sur la gestion [des](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/curate-share/curate.html)projets.

![](assets/share-proj-modal.png)

## Partager sur des groupes de destinataires

Tous les utilisateurs peuvent partager des projets dans des groupes, qui sont un ensemble de destinataires. Dans Adobe Analytics, les groupes sont définis par profils de produits dans Adobe Experience Cloud.

* Les administrateurs peuvent partager des données avec n’importe quel groupe, y compris &quot;Tous&quot;.
* Les non-administrateurs peuvent partager avec des groupes dont ils sont membres, à l’exception de &quot;Tous&quot;.

## Partage de projets dans le gestionnaire de projets

Les projets peuvent également être partagés à partir de **[!UICONTROL Composants]>[!UICONTROL Projets]**. Un seul projet peut être partagé en suivant les mêmes étapes que celles décrites ci-dessus.

Si plusieurs projets sont sélectionnés pour être partagés, des destinataires seront ajoutés à la liste existante de destinataires pour chaque projet. Par exemple :

* Le projet A est partagé avec les utilisateurs 1, 2, 3
* Le projet B est partagé avec les utilisateurs 4, 5, 6
* Les projets A et B étant sélectionnés, les utilisateurs 4 et 7 sont ajoutés aux listes destinataires. La nouvelle liste de destinataire pour chaque projet est désormais :
   * Projet A : 1, 2, 3, 4, 7
   * Projet B : 4, 5, 6, 7
   ![](assets/mult-proj-sharing.png)
