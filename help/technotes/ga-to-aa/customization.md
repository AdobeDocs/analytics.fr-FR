---
title: Personnalisation des rapports dans Adobe Analytics
description: Découvrez comment personnaliser des rapports dans Adobe Analytics
translation-type: ht
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Personnalisation des rapports

Sur les plateformes tierces, telles que Google Analytics, plusieurs options de personnalisation sont disponibles. Ces personnalisations permettent à l’utilisateur de créer des tableaux de bord, des rapports personnalisés, des rapports enregistrés et des alertes personnalisées. Comme Analysis Workspace permet aux utilisateurs de créer des rapports à partir d’un canevas vierge, la plupart des personnalisations sont directement intégrées à l’outil.

Cette page part du principe que l’utilisateur maîtrise les bases de l’utilisation d’Analysis Workspace. Voir [Création d’un rapport de base dans Analysis Workspace pour les utilisateurs de Google Analytics](reports/create-report.md) si vous ne connaissez pas encore l’outil dans Adobe Analytics.

## Tableaux de bord

L’architecture d’Analysis Workspace est similaire au concept des widgets des tableaux de bord. Les projets d’Analysis Workspace sont équivalents aux tableaux de bord de Google Analytics. Les visualisations d’Analysis Workspace sont équivalentes aux widgets de Google Analytics.

### Ajout de contenu à un projet

1. Cliquez sur l’icône Visualisations à gauche et faites glisser la visualisation de votre choix sur l’espace de travail.
2. Cliquez sur l’icône Composants à gauche et faites glisser les dimensions et mesures de votre choix sur la visualisation pour la remplir de données.
3. Faites glisser les bords de la visualisation pour la redimensionner, et faites glisser le titre de la visualisation pour le déplacer.

Tous les widgets Google Analytics sont disponibles dans Analysis Workspace :

* Le **widget Mesure** est à peu près équivalent à la visualisation Synthèse des chiffres.
* Le **widget Chronologie** est à peu près équivalent à la visualisation Ligne.
* Le **widget Geomap** est à peu près équivalent à la visualisation Carte.
* Le **widget Tableau** est à peu près équivalent à la visualisation Tableau à structure libre.
* Le **widget circulaire** est à peu près équivalent à la visualisation Anneau.
* Le **widget Barre** est peu près équivalent à la visualisation Barre.

Analysis Workspace inclut de nombreuses autres options de visualisation pour présenter les données de la manière la plus adaptée à vos besoins de création de rapports. Pour plus d’informations, voir [Visualisations dans Analysis Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) dans le guide d’utilisation.

### Partage de projets

Une fois que vous avez terminé d’ajouter du contenu à un projet, vous pouvez le partager.

* Pour partager le projet avec vos collègues, accédez à Partager > Partager le projet. Les destinataires sont d’autres utilisateurs de votre entreprise qui possèdent des comptes Adobe Analytics.
* Pour partager votre projet via un lien, accédez à Partager > Obtenir le lien du projet. Notez que cela nécessite également une connexion à Adobe Analytics au sein de votre entreprise.

### Exportation de projets

Outre le format PDF, Analysis Workspace propose une exportation au format CSV.

1. Cliquez sur *[!UICONTROL Partager]* > *[!UICONTROL Envoyer le fichier maintenant]*. Une fenêtre modale s’ouvre.
2. Précisez le type de fichier et les destinataires.
3. Cliquez sur [!UICONTROL Envoyer maintenant].

## Rapports personnalisés

Lors de la création d’un rapport personnalisé dans Google Analytics, les champs requis sont similaires au processus de création d’une visualisation dans l’espace de travail. Les définitions de dimensions, de mesures et de filtres sont similaires dans toutes les plateformes. Dans Analysis Workspace, au lieu de sélectionner des dimensions et des mesures dans une liste, les dimensions et les mesures sont glissées sur un tableau à structure libre.

### Mesures calculées dans les rapports personnalisés

Les rapports personnalisés sont l’un des rares domaines de Google Analytics qui autorise l’utilisation de mesures calculées. Comme Analysis Workspace fonctionne comme un canevas, les mesures calculées fonctionnent rétroactivement et dans n’importe quel contexte.

Pour créer une mesure calculée :

1. Cliquez sur l’icône **+** près de la liste des mesures pour ouvrir le créateur de mesures calculées.
2. Attribuez un nom à votre mesure calculée et spécifiez un format.
3. Faites glisser des composants de mesure vers la zone de définition et utilisez les listes déroulantes entre chaque composant pour désigner un opérateur.
4. Une fois que la mesure calculée contient la formule souhaitée, cliquez sur Enregistrer pour revenir à votre espace de travail.
5. Faites glisser la mesure calculée nouvellement définie sur l’espace de travail.

   Pour en savoir plus sur les [mesures calculées](/help/components/c-variables/c-metrics/calculated-metric.md), voir le guide d’utilisation des composants.

## Alertes personnalisées

Les alertes sont disponibles sur les deux plateformes. Dans Adobe Analytics, utilisez le menu de navigation de l’en-tête et accédez à *[!UICONTROL Composants]* > *[!UICONTROL Alertes]*. Pour plus d’informations, voir [Alertes intelligentes](/help/components/c-alerts/intellligent-alerts.md) dans le guide d’utilisation des composants.
