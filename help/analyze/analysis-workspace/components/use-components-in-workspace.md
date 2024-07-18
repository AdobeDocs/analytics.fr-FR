---
description: Découvrez comment ajouter des composants à un projet dans Analysis Workspace
title: Utiliser des composants dans Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: fb56e794-67e3-4f85-960e-b90684300fa0
source-git-commit: 9fcebd7a8fb3a3d98eebef53a748c8ac585cbcd1
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 16%

---

# Utiliser des composants dans Analysis Workspace

Les composants constituent les données réelles de tout projet dans Analysis Workspace. Les composants se composent de dimensions, de mesures, de segments et de périodes. Vous pouvez ajouter des composants à un projet en les faisant glisser dans des visualisations ou des panneaux.

Pour obtenir des informations d’aperçu sur les types de composants que vous pouvez ajouter, voir [Présentation des composants](/help/analyze/analysis-workspace/components/analysis-workspace-components.md).

>[!TIP]
>
>Pour plus d’informations sur chaque composant, sélectionnez l’icône Informations en regard du nom d’un composant dans le rail de gauche d’Analysis Workspace ou consultez le [Guide des composants Analytics](/help/components/home.md).

## Commencer à ajouter des composants à un projet

1. [Créez un projet dans Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) si ce n’est déjà fait.

1. [Ajoutez un panneau](/help/analyze/analysis-workspace/c-panels/panels.md) ou [ajoutez une visualisation](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) au projet dans Analysis Workspace.

   Si vous ajoutez un composant à un projet vierge, une visualisation de tableau à structure libre est automatiquement créée.

1. Sélectionnez l’icône **[!UICONTROL Composants]** dans le rail de gauche.

   ![](assets/build-components.png)

1. Faites défiler l’écran jusqu’au composant que vous souhaitez ajouter ou recherchez-le, puis faites-le glisser vers un panneau ou une visualisation dans votre projet.

1. (Facultatif) Faites glisser un composant vers la zone de dépôt de segments dans un en-tête de panneau.

   Les segments s’appliquent à tout le contenu du panneau.

   Pour plus d’informations sur l’utilisation de la zone de dépôt de segments sur un panneau pour filtrer votre panneau, voir [Zone de dépôt](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) dans la [présentation des panneaux](/help/analyze/analysis-workspace/c-panels/panels.md).

   ![déposer un segment dans la zone de dépôt](assets/segment-dropzone.png)

1. Pour plus d’informations, passez à l’une des sections suivantes, selon le type de composant que vous ajoutez :

   * [Ajout de dimensions à un projet](#add-dimensions-to-a-project)

   * [Ajout de mesures à un projet](#add-metrics-to-a-project)

   * [Ajout de segments à un projet](#add-segments-to-a-project)

   * [Ajout de périodes à un projet](#add-date-ranges-to-a-project)

## Ajout de dimensions à un projet

[Dimensions](/help/components/dimensions/overview.md) sont des variables dans Adobe Analytics qui contiennent généralement des valeurs de chaîne. Les dimensions courantes comprennent [Page](/help/components/dimensions/page.md), [Domaine référent](/help/components/dimensions/referring-domain.md) ou une [eVar](/help/components/dimensions/evar.md). En revanche, les [mesures](/help/components/metrics/overview.md) contiennent des valeurs numériques liées à une dimension. Un rapport de base présente des lignes de valeurs de chaîne (dimension) en fonction d’une colonne de valeurs numériques (mesure).

1. Commencez à ajouter une dimension à votre projet dans Analysis Workspace, comme décrit dans [Commencer à ajouter des composants à un projet](#begin-adding-components-to-a-project).

1. Choisissez l’une des méthodes suivantes pour ajouter des dimensions et déterminer le type de données à analyser :

   * Faites glisser une dimension sur une visualisation (un tableau à structure libre, par exemple) dans Analysis Workspace.

     ![Ajouter des dimensions à un projet](assets/add-dimensions.png)

   * Faites glisser une ou plusieurs dimensions du rail de gauche sur la zone de dépôt des segments pour créer un segment ad hoc, comme décrit dans la section [Ajout de segments à un projet](#add-segments-to-a-project).

     ![déposer un segment dans la zone de dépôt](assets/segment-dropzone.png)

1. (Facultatif) Vous pouvez ventiler des dimensions et des éléments de dimension dans Analysis Workspace avec d’autres composants.

   Pour plus d’informations, voir [Ventilation des dimensions](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md).

Pour plus d’informations sur l’utilisation des dimensions dans Analysis Workspace, voir [Aperçu des dimensions](/help/analyze/analysis-workspace/components/dimensions/view-dimensions.md), [Ventilation des dimensions](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) et [Dimensions de répartition du temps](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md).

## Ajout de mesures à un projet

[Les mesures](/help/analyze/analysis-workspace/components/apply-create-metrics.md) vous permettent de quantifier les points de données dans Analysis Workspace. Elles sont généralement utilisées comme colonnes dans une visualisation et liées aux dimensions.

Pour ajouter une mesure à un projet dans Analysis Workspace :

1. Commencez à ajouter une mesure à votre projet dans Analysis Workspace, comme décrit dans [Commencer à ajouter des composants à un projet](#begin-adding-components-to-a-project).

1. Choisissez l’une des méthodes suivantes pour ajouter une mesure dans Analysis Workspace :

   * Faites glisser une mesure sur la zone de dépôt des mesures dans un tableau à structure libre vide pour afficher les tendances de cette mesure sur la période du projet.

     ![Ajouter une mesure à un projet](assets/add-metrics.png)

   * Faire glisser une mesure lorsqu’une dimension est présente pour la comparer à chaque élément de la dimension.

   * Faire glisser une mesure au-dessus d’un en-tête de mesure existant pour le remplacer.

   * Faire glisser une mesure près d’un en-tête pour afficher les deux côte à côte.

Pour plus d’informations sur l’utilisation des mesures dans Analysis Workspace, voir [Mesures](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

## Ajout de segments à un projet

Les [segments](/help/components/segmentation/seg-overview.md) vous permettent d’identifier des sous-ensembles de visiteurs en fonction de caractéristiques ou d’interactions spécifiques.

Vous pouvez utiliser les segments dans Analysis Workspace de l’une des manières suivantes :

### Ajout de segments à un panneau

Lorsque vous ajoutez des segments à un panneau, ils s’appliquent à tout le contenu du panneau.

Pour plus d’informations sur l’utilisation de la zone de dépôt de segments sur un panneau pour filtrer votre panneau, voir [Zone de dépôt](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) dans la [présentation des panneaux](/help/analyze/analysis-workspace/c-panels/panels.md).

### Ajout de segments à une colonne d’un tableau à structure libre

Lorsque vous ajoutez des segments à une colonne d’un tableau à structure libre, les segments s’appliquent à tout le contenu de la colonne du tableau.

### Utilisation de segments lors de la création de mesures calculées

Dans le créateur de mesures calculées, vous pouvez appliquer des segments dans votre définition de mesure.

Pour plus d’informations, voir [Mesures segmentées](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md).

## Ajout de périodes à un projet

[Les plages de dates](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md) déterminent la période de création de rapports dans Analysis Workspace et peuvent être appliquées à un ou plusieurs panneaux au sein d’un projet.

Par défaut, chaque panneau comprend une plage de dates. Il existe plusieurs façons de mettre à jour une période pour un panneau. Pour mettre à jour une période pour un panneau dans Analysis Workspace, faites glisser un composant de période depuis le rail de gauche :

1. Commencez à ajouter une période à votre projet dans Analysis Workspace, comme décrit dans [Commencer à ajouter des composants à un projet](#begin-adding-components-to-a-project).

1. Faites glisser une plage de dates du rail de gauche vers la plage de dates actuelle dans la partie supérieure droite du panneau.

   ![déposer une plage de dates](assets/daterange-drop.png)

Pour plus d’informations sur l’utilisation des calendriers et des plages de dates dans Analysis Workspace, consultez la [présentation du calendrier et des plages de dates](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md).
