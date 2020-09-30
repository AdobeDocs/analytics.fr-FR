---
description: Un panneau est un ensemble de tableaux et de visualisations.
title: Panneaux - Aperçu
translation-type: tm+mt
source-git-commit: 56ca9fa36db9d7dd126808280ba17f29f4b787d9
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 18%

---


# Panneaux - Aperçu

A [!UICONTROL panel] is a collection of tables and visualizations. Vous pouvez accéder aux panneaux à partir de l’icône supérieure gauche dans Workspace. Les panneaux sont utiles pour organiser vos projets en fonction des périodes, des suites de rapports ou des cas d’utilisation des analyses. Les types de panneau suivants sont disponibles en Analysis Workspace :

| Nom du panneau | Description |
|---|---|
| [Panneau vierge](blank-panel.md) | Choisissez parmi les panneaux et visualisations disponibles pour début votre analyse. |
| [Panneau Quick Insights](quickinsight.md) | Construisez rapidement un tableau de forme libre et une visualisation d’accompagnement afin d’analyser et de découvrir des informations plus rapidement. |
| [Panneau Analytics for Target](a4t-panel.md) | Analysez les activités et les expériences Target dans Analysis Workspace. |
| [Panneau d’attribution](attribution.md) | Comparer et visualiser rapidement n’importe quel nombre de modèles d’attribution en utilisant n’importe quelle dimension ou mesure de conversion. |
| [Panneau à structure libre](freeform-panel.md) | Procédez à des comparaisons et à des répartitions sans aucune restriction, puis ajoutez des visualisations pour enrichir vos données. |
| [Panneau Visionneuses simultanées de médias](media-concurrent-viewers.md) | Analysez les viewers simultanés sur le long terme, avec des informations sur la simultanéité la plus élevée et sur la capacité à ventiler et à comparer. |
| [Panneau de comparaison des segments](c-segment-comparison/segment-comparison.md) | Comparez rapidement deux segments sur tous les points de données afin de rechercher automatiquement les différences pertinentes. |

![](assets/panel-overview.png)

[!UICONTROL Les panneaux d’informations]rapides, [!UICONTROL vierges] et [!UICONTROL à structure libre] sont des emplacements idéaux pour début de votre analyse, tandis que les [!UICONTROL Analytics pour la Cible], Attribution IQ, les visionneuses simultanées de contenu multimédia et les de comparaison de segments se prêtent à des analyses plus avancées.  Un bouton `"+"` est disponible dans les projets afin que vous puissiez ajouter des panneaux vierges à tout moment.

The default starting panel is the [!UICONTROL Freeform] panel, but you can make the [blank panel](/help/analyze/analysis-workspace/c-panels/blank-panel.md) your default as well.

## Suite de rapports de panneau {#report-suite}

Les tableaux et les visualisations d’un panneau dérivent des données de la suite [!UICONTROL de] rapports sélectionnée dans l’angle supérieur droit du panneau. La suite de rapports détermine également les composants disponibles dans le rail de gauche. Dans un projet, vous pouvez utiliser une ou [plusieurs suites](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) de rapports en fonction des cas d’utilisation de vos analyses.

![](assets/panel-report-suite.png)

## Calendrier du panneau {#calendar}

Le calendrier du panneau contrôle la plage de rapports des tableaux et des visualisations dans un panneau.

Remarque : Si un composant de plage de dates (violet) est utilisé dans un tableau, une visualisation ou une zone de dépôt de panneau, il remplace le calendrier du panneau.

![](assets/panel-calendar.png)

## Zone de liste déroulante {#dropzone}

La zone de liste déroulante des panneaux vous permet d’appliquer des filtres de segments et des menus déroulants à tous les tableaux et visualisations d’un panneau. Vous pouvez appliquer un ou plusieurs filtres à un panneau. Le titre au-dessus de chaque filtre peut être modifié en cliquant sur le crayon d&#39;édition ou vous pouvez cliquer avec le bouton droit pour le supprimer complètement.

### Filtres de segments

Faites glisser un segment du rail de gauche vers la zone de dépôt du panneau pour commencer à filtrer le panneau.

![](assets/segment-filter.png)

### Filtres de segments ad hoc

Vous pouvez également faire glisser des composants non liés aux segments directement dans la zone de dépôt afin de créer des segments **** ad hoc, ce qui vous permet de gagner du temps et de gagner du temps dans le créateur de segments. Les segments ainsi créés sont automatiquement définis comme des segments de niveau accès. Cette définition peut être modifiée en cliquant sur l’icône d’informations (i) en regard du segment, puis sur l’icône d’édition en forme de crayon et en la modifiant dans le créateur de segments.

Les segments ad hoc sont locaux pour le projet et ne s’afficheront pas dans votre rail de gauche à moins que vous ne les rendiez publics.

![](assets/adhoc-segment-filter.png)

### Filtres déroulants {#dropdown-filter}

Outre les filtres de segments, les filtres **** déroulants vous permettent d’interagir avec les données de manière contrôlée. Par exemple, vous pouvez ajouter un filtre déroulant pour les types de périphériques mobiles afin de segmenter le panneau par tablette, téléphone mobile ou bureau.

Les filtres déroulants peuvent également servir à consolider de nombreux projets en un seul. Par exemple, si plusieurs versions d’un même projet sont appliquées avec des segments Pays différents, vous pouvez consolider toutes les versions en un seul projet et ajouter un filtre déroulant Pays.

![](assets/dropdown-filter-intro.png)

**Créez et utilisez des filtres déroulants :**

![](assets/create-dropdown.png)

1. Pour créer un filtre déroulant à l’aide d’éléments [!UICONTROL de]Dimension, tels que des valeurs dans la dimension Canal  marketing, cliquez sur l’icône de flèche vers la droite située en regard de votre dimension dans le rail de gauche. Cette opération expose tous les éléments disponibles. Sélectionnez un ou plusieurs éléments de composant dans le rail de gauche et déposez-les dans la zone de dépôt du panneau **tout en maintenant la touche** Maj enfoncée. Les composants seront alors transformés en filtre déroulant, plutôt qu’en un seul segment.
1. Pour créer un filtre déroulant à l’aide d’autres composants tels que les mesures, les segments ou les plages de dates, sélectionnez un type de composant dans le rail de gauche et déposez dans la zone de liste déroulante du panneau **tout en maintenant la touche** Maj enfoncée.
1. Sélectionnez l’une des options de la liste déroulante pour modifier les données du panneau. Vous pouvez également choisir de ne pas filtrer les données du panneau en sélectionnant **[!UICONTROL Pas de filtre]**.

[Regardez la vidéo](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html) pour en savoir plus sur l&#39;ajout de filtres déroulants à votre projet.
