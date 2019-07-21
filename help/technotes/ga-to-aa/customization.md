---
title: Personnalisation des rapports dans Adobe Analytics
description: Découvrez comment personnaliser les rapports dans Adobe Analytics
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# Personnalisation des rapports

Dans les plateformes tierces telles que Google Analytics, plusieurs options de personnalisation sont disponibles. Ces personnalisations permettent à un utilisateur de créer des tableaux de bord, des rapports personnalisés, des rapports enregistrés et des alertes personnalisées. Comme Analysis Workspace permet aux utilisateurs de créer des rapports à partir d'un canevas vierge, la plupart des personnalisations sont créées directement dans l'outil.

Cette page suppose que l'utilisateur maîtrise de base l'utilisation d'Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](reports/create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Tableaux de bord

L'architecture de l'espace de travail d'analyse est similaire au concept de widgets de tableau de bord. Les projets dans Analysis Workspace sont approximativement équivalents aux tableaux de bord dans Google Analytics. Les visualisations dans Analysis Workspace sont approximativement équivalentes aux widgets dans Google Analytics.

### Ajout de contenu à un projet

1. Cliquez sur l'icône Visualisations à gauche et faites glisser la visualisation souhaitée sur l'espace de travail.
2. Cliquez sur l'icône Composants à gauche et faites glisser les dimensions et mesures souhaitées sur la visualisation pour la remplir avec des données.
3. Faites glisser les bords de la visualisation pour la redimensionner, puis faites glisser le titre de la visualisation pour le déplacer.

Tous les widgets Google Analytics sont disponibles dans Analysis Workspace :

* The **Metric widget** is approximately equal to the Summary Number visualization.
* The **Timeline widget** is approximately equal to the Line visualization.
* The **Geomap widget** is approximately equal to the Map visualization.
* The **Table widget** is approximately equal to the Freeform Table visualization.
* The **Pie widget** is approximately equal to the Donut visualization.
* The **Bar widget** is approximately equal to the Bar visualization.

Analysis Workspace offre beaucoup d'autres options de visualisation pour présenter les données de manière optimale en fonction de vos besoins de rapports. See [Visualizations in Analysis Workspace](../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) in the Analyze User Guide for more information.

### Partage de projets

Une fois que vous avez fini d'ajouter du contenu à un projet, vous pouvez le partager.

* Pour partager le projet avec vos collègues, cliquez sur Partager &gt; Partager le projet. Les destinataires sont d'autres utilisateurs de votre organisation qui disposent de comptes Adobe Analytics.
* Pour partager votre projet via un lien, cliquez sur Partager &gt; Obtenir le lien du projet. Notez qu'il est toujours nécessaire de se connecter à Adobe Analytics au sein de votre organisation.

### Exportation de projets

Outre le format PDF, Analysis Workspace offre une exportation au format CSV.

1. Click *[!UICONTROL Share]* &gt; *[!UICONTROL Send File Now]*, which opens a modal window.
2. Indiquez le type de fichier et les destinataires.
3. Click [!UICONTROL Send Now].

## Rapports personnalisés

Lors de la création d'un rapport personnalisé dans Google Analytics, les champs requis sont similaires au processus lors de la création d'une visualisation dans l'espace de travail. Les définitions de dimensions, de mesures et de filtres sont similaires entre les plateformes. Dans Analysis Workspace, au lieu de sélectionner des dimensions et des mesures issues d'une liste, les dimensions et les mesures sont glissées sur un tableau à structure libre.

### Mesures calculées dans les rapports personnalisés

Les rapports personnalisés sont l'une des quelques zones dans Google Analytics qui permettent l'utilisation de mesures calculées. Comme Analysis Workspace fonctionne comme un canevas, les mesures calculées fonctionnent de manière rétroactive et dans n'importe quel contexte.

Pour créer une mesure calculée :

1. Click the **+** icon near the metric list to open the Calculated Metric Builder.
2. Attribuez un nom à votre mesure calculée et indiquez un format.
3. Faites glisser les composants de mesure vers la zone de définition et utilisez les listes déroulantes entre chaque composant pour désigner un opérateur.
4. Une fois la mesure calculée contenant la formule souhaitée, cliquez sur Enregistrer pour revenir à votre espace de travail.
5. Faites glisser la mesure calculée nouvellement définie sur l'espace de travail.

   Learn more about [Calculated Metrics](../../components/c-variables/c-metrics/calculated-metric.md) in the Components user guide.

## Alertes personnalisées

Les alertes sont disponibles sur les deux plates-formes. In Adobe Analytics, use the header navigation menu and go to *[!UICONTROL Components]* &gt; *[!UICONTROL Alerts]*. See [Intelligent Alerts](../../components/c-alerts/intellligent-alerts.md) in the Components User Guide for more information.
