---
title: Personnalisation des rapports dans Adobe Analytics
description: Découvrez comment personnaliser des rapports dans Adobe Analytics
translation-type: tm+mt
source-git-commit: 3211598c2ff43493b329a9be4fb6877ae29cf08b
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 78%

---


# Personnalisation des rapports

Sur les plateformes tierces, telles que Google Analytics, plusieurs options de personnalisation sont disponibles. Ces personnalisations permettent à l’utilisateur de créer des tableaux de bord, des rapports personnalisés, des rapports enregistrés et des alertes personnalisées. Comme Analysis Workspace permet aux utilisateurs de créer des rapports à partir d’un canevas vierge, la plupart des personnalisations sont directement intégrées à l’outil.

This page assumes the user has a basic knowledge of using [!UICONTROL Analysis Workspace]. Voir [Création d’un rapport de base dans Analysis Workspace pour les utilisateurs de Google Analytics](reports/create-report.md) si vous ne connaissez pas encore l’outil dans Adobe Analytics.

## Tableaux de bord

The [!UICONTROL Analysis Workspace] architecture is built similar to the concept of dashboard widgets. Projects in [!UICONTROL Analysis Workspace] are the approximate equivalent to dashboards in Google Analytics. Visualizations in [!UICONTROL Analysis Workspace] are the approximate equivalent of widgets in Google Analytics.

### Ajout de contenu à un projet

1. Click the [!UICONTROL Visualizations] icon on the left and drag the desired visualization onto the workspace.
2. Click the [!UICONTROL Components] icon on the left and drag the desired dimensions and metrics onto the visualization to populate it with data.
3. Faites glisser les bords de la visualisation pour la redimensionner, et faites glisser le titre de la visualisation pour le déplacer.

All Google Analytics widgets are available in [!UICONTROL Analysis Workspace]:

* Le **widget Mesure** est à peu près équivalent à la visualisation Synthèse des chiffres.
* Le **widget Chronologie** est à peu près équivalent à la visualisation Ligne.
* Le **widget Geomap** est à peu près équivalent à la visualisation Carte.
* Le **widget Tableau** est à peu près équivalent à la visualisation Tableau à structure libre.
* Le **widget circulaire** est à peu près équivalent à la visualisation Anneau.
* Le **widget Barre** est peu près équivalent à la visualisation Barre.

[!UICONTROL Analysis Workspace inclut de nombreuses autres options de visualisation pour présenter les données de la manière la plus adaptée à vos besoins de création de rapports. ] Pour plus d’informations, voir [Visualisations dans Analysis Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) dans le guide d’utilisation.

### Partage de projets

Une fois que vous avez terminé d’ajouter du contenu à un projet, vous pouvez le partager.

* To share the project with your colleagues, go to **[!UICONTROL Share > Share Project]**. Les destinataires sont d’autres utilisateurs de votre entreprise qui possèdent des comptes Adobe Analytics.
* To share your project via a link, go to **[!UICONTROL Share > Get Project Link]**. Notez que cela nécessite également une connexion à Adobe Analytics au sein de votre entreprise.

### Exportation de projets

In addition to PDF, [!UICONTROL Analysis Workspace] offers a CSV export.

1. Cliquez sur *[!UICONTROL Partager]* > *[!UICONTROL Envoyer le fichier maintenant]*. Une fenêtre modale s’ouvre.
2. Précisez le type de fichier et les destinataires.
3. Cliquez sur [!UICONTROL Envoyer maintenant].

## Rapports personnalisés

Lors de la création d’un rapport personnalisé dans Google Analytics, les champs requis sont similaires au processus de création d’une visualisation dans l’espace de travail. Les définitions de dimensions, de mesures et de filtres sont similaires dans toutes les plateformes. Dans Analysis Workspace, au lieu de sélectionner des dimensions et des mesures dans une liste, les dimensions et les mesures sont glissées sur un tableau à structure libre.

### Mesures calculées dans les rapports personnalisés

Les rapports personnalisés sont l’un des rares domaines de Google Analytics qui autorise l’utilisation de mesures calculées. Comme Analysis Workspace fonctionne comme un canevas, les mesures calculées fonctionnent rétroactivement et dans n’importe quel contexte.

Pour créer une mesure calculée :

1. Cliquez sur l’icône **+**[!UICONTROL  près de la liste des mesures pour ouvrir le créateur de mesures calculées].
2. Attribuez un nom à votre mesure calculée et spécifiez un format.
3. Faites glisser des composants de mesure vers la zone de définition et utilisez les listes déroulantes entre chaque composant pour désigner un opérateur.
4. Une fois que la mesure calculée contient la formule souhaitée, cliquez sur Enregistrer pour revenir à votre espace de travail.
5. Faites glisser la mesure calculée nouvellement définie sur l’espace de travail.

   Pour en savoir plus sur les [mesures calculées](/help/components/c-variables/c-metrics/calculated-metric.md), voir le guide d’utilisation des composants.

## Alertes personnalisées

Les alertes sont disponibles sur les deux plateformes. Dans Adobe Analytics, utilisez le menu de navigation de l’en-tête et accédez à *[!UICONTROL Composants]* > *[!UICONTROL Alertes]*. Pour plus d’informations, voir [Alertes intelligentes](/help/components/c-alerts/intellligent-alerts.md) dans le guide d’utilisation des composants.
