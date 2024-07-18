---
description: Découvrir les principes de base de la création d’un projet dans Analysis Workspace
title: Créer des projets
feature: Workspace Basics
role: User, Admin
exl-id: 24193013-1361-43fc-b129-c44f207d9101
source-git-commit: 273fea86cde8880d9c9e03ac9c6a99b75f70f6cd
workflow-type: tm+mt
source-wordcount: '770'
ht-degree: 100%

---

# Créer des projets dans Analysis Workspace

Les [projets](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) dans Analysis Workspace vous permettent d’afficher des analyses commerciales essentielles qui peuvent être partagées avec des parties prenantes au sein de votre entreprise ou en dehors.

Pour des informations générales sur la manière de commencer à utiliser Analysis Workspace, consultez la [Vue d’ensemble d’Analysis Workspace](/help/analyze/analysis-workspace/home.md).

Les sections suivantes expliquent comment créer un projet et commencer à ajouter les blocs de création clés des projets Analysis Workspace : panneaux, visualisations et composants.

## Créer un projet à partir d’un projet vierge ou d’un rapport

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Workspace**].

1. Choisissez de créer un projet vierge ou de créer un projet à partir d’un rapport :

   +++Créer un projet vierge

   1. Dans l’onglet [!UICONTROL **Workspace**], sélectionnez l’onglet [!UICONTROL **Projets**] sur le côté gauche de la page, puis [!UICONTROL **Créer un projet**].

   1. Choisissez de créer un projet vierge ou une carte de performance mobile vierge.

      * **Projet vierge** : si vous prévoyez de partager votre analyse à partir du navigateur.
      * [**Carte de performance mobile vierge**](/help/analyze/mobile-app/curator.md) : si vous prévoyez de partager votre analyse à partir de l’application mobile des tableaux de bord Adobe Analytics.

   1. Sélectionnez [!UICONTROL **Créer**].

+++

   +++Créer un projet à partir d’un rapport

   1. Dans l’onglet [!UICONTROL **Workspace**], sélectionnez l’onglet [!UICONTROL **Rapports**] sur le côté gauche de la page.

   1. Recherchez ou accédez au rapport à utiliser, puis sélectionnez-le lorsqu’il apparaît.

      Un ensemble de rapports standard est disponible par défaut. En outre, votre entreprise peut avoir créé des rapports personnalisés parmi lesquels choisir.

   1. Sélectionnez [!UICONTROL **Projet**] > [!UICONTROL **Enregistrer**] pour enregistrer le rapport en tant que nouveau projet.

      Pour plus d’informations sur les rapports, consultez « l’onglet Naviguer dans les rapports » sur la [page de destination d’Adobe Analytics](/help/analyze/landing.md).

+++

1. Vous devez ensuite ajouter des panneaux, des visualisations et des composants à votre projet. Tout d’abord, ajoutez des panneaux à votre projet dans Analysis Workspace, comme décrit dans la section [Ajouter des panneaux au projet](#add-panels-to-the-project). Vous pouvez ensuite ajouter des visualisations à n’importe quel panneau. Enfin, vous pouvez ajouter des composants à n’importe quel panneau ou visualisation.

## Ajouter des panneaux au projet {#panels}

Les [panneaux](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=fr) sont la base de tout projet dans Analysis Workspace. Les panneaux permettent d’organiser le contenu (visualisations et composants) d’un projet.

De nombreux panneaux fournis dans Analysis Workspace génèrent un ensemble complet d’analyses sur la base de quelques entrées d’utilisateur ou d’utilisatrice.

Pour ajouter un panneau :

1. Sélectionnez l’icône [!UICONTROL **Panneaux**] dans le rail de gauche.

   ![](assets/build-panels.png)

1. Recherchez le panneau à ajouter. Lorsqu’il apparaît dans le rail de gauche, faites-le glisser dans votre projet.

1. Ajoutez des visualisations à votre panneau, comme décrit dans la section [Ajouter des visualisations au projet](#add-visualizations-to-the-project).

   Vous pouvez également ajouter des composants directement à un panneau, comme décrit dans la section [Ajouter des composants au projet](#add-components-to-the-project).

## Ajouter des visualisations au projet

Des [visualisations](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=fr) (telles qu’un tableau à structure libre, un graphique à barres ou linéaire) peuvent être utilisées pour donner vie aux données visuellement.

>[!TIP]
>
>Les tableaux à structure libre sont le type de visualisation le plus courant et constituent la base de l’analyse de données interactive. Pour en savoir plus sur l’utilisation des tableaux à structure libre dans Analysis Workspace, voir [Tableau à structure libre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md).

Pour ajouter une visualisation :

1. Sélectionnez l’icône **[!UICONTROL Visualisations]** dans le rail de gauche.

   ![](assets/build-visualizations.png)

1. Recherchez la visualisation à ajouter. Lorsqu’elle apparaît dans le rail de gauche, faites-la glisser vers un panneau de votre projet.

1. Ajoutez des composants à la visualisation, comme décrit dans la section [Ajouter des composants au projet](#add-components-to-the-project).

## Ajouter des composants au projet

Les [composants](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) représentent les données réelles de n’importe quel projet. Vous pouvez ajouter des composants aux visualisations ou aux panneaux.

>[!TIP]
>
>Pour plus d’informations sur chaque composant, sélectionnez l’icône Informations située en regard du nom d’un composant dans le rail de gauche ou reportez-vous au [Guide des composants Analytics](/help/components/home.md).

Vous trouverez ci-dessous des informations de base sur l’ajout d’un composant à un projet dans Analysis Workspace. Pour plus d’informations sur l’ajout des différents types de composants (dimensions, mesures, segments et périodes), voir [Utiliser des composants dans Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).

Pour ajouter un composant à un projet dans Analysis Workspace :

1. Sélectionnez l’icône **[!UICONTROL Composants]** dans le rail de gauche.

   ![](assets/build-components.png)

1. Faites défiler l’écran jusqu’au composant que vous souhaitez ajouter ou recherchez-le, puis faites-le glisser vers un panneau ou une visualisation dans votre projet.

   Par exemple, vous pouvez faire glisser un segment vers la zone de dépôt des segments dans un en-tête de panneau.

   ![déposer un segment dans la zone de dépôt](assets/segment-dropzone.png)

   Pour plus d’informations sur l’ajout de composants aux projets, voir [Utiliser des composants dans Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).

1. (Facultatif) Partagez le projet, comme décrit dans la section [Enregistrer et partager le projet](#save-and-share-the-project).

## Enregistrer et partager le projet

Lorsque vous créez une analyse dans Analysis Workspace, votre travail est [enregistré automatiquement](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).

Une fois que vous avez terminé de créer le projet et que celui-ci collecte des informations exploitables, il est prêt à être utilisé par d’autres personnes. Vous pouvez partager le projet avec des utilisateurs ou utilisatrices, et des groupes de votre organisation, ou même avec des personnes en dehors de votre organisation. Pour plus d’informations sur le partage d’un projet, voir [Partager des projets](/help/analyze/analysis-workspace/curate-share/share-projects.md).
