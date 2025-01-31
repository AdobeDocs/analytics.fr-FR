---
description: Utilisation de segments dans Analysis Workspace.
title: Segments
feature: Segmentation
role: User, Admin
exl-id: 67112e13-4d0a-4d77-be50-496c3d28779c
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 81%

---


# Segments {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

Vous pouvez créer différents types de segments dans Workspace, selon la complexité requise et selon quʼils doivent sʼappliquer uniquement à ce projet, etc. Voici un résumé des types de segments :

| Type de segment | Emplacement de création | Applicable où ? | Conditions d’utilisation |
| --- | --- | --- | --- |
| Segment de la liste des composants | Cliquez sur « + » pour accéder au [Créateur de segments](/help/components/segmentation/segmentation-workflow/seg-build.md). | Tous vos projets Workspace | Pour les segments plus complexes et les segments séquentiels |
| Segment rapide | [Créateur de segments rapide](/help/analyze/analysis-workspace/components/segments/quick-segments.md) | Uniquement pour le projet, mais possibilité de lʼenregistrer et de lʼajouter à votre liste de segments. | Peut être utilisé pour les segments ad hoc à règle unique (avec glisser-déposer) ou pour ajouter/modifier plusieurs règles (en cliquant sur l’icône Segment) |
| Segment basé sur les mesures calculées | [Créateur de mesures calculées](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/metrics-with-segments.html?lang=fr) | À une mesure calculée individuelle | Application du ou des segments dans la définition de votre mesure |
| Segment basé sur une suite de rapports virtuelle | [Créateur de suites de rapports virtuelles](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html?lang=fr) | À une suite de rapports virtuelle individuelle | Application du ou des segments dans votre définition de suite de rapports virtuelle |

## Vidéos

>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Utilisation de segments dans Analysis Workspace](https://video.tv.adobe.com/v/23977?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Recherche et création de segments](https://video.tv.adobe.com/v/334092?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Périodes flottantes dans le segment](https://video.tv.adobe.com/v/25403?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Création de segments {#section_693CFADA668B4542B982446C2B4CF0F5}

Vous pouvez créer différents types de segments dans Analysis Workspace :

* [Segments rapides](/help/analyze/analysis-workspace/components/segments/quick-segments.md)
* Segments standard de la liste des composants : ils sont créés dans le Créateur de segments et terminent dans la bibliothèque de segments (voir ci-dessous).

### Création de segments de la liste des composants {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

Le rail des segments sous le menu Composants sʼaffiche

* Segments que vous ou votre société avez créés
* Modèles de segment, comme indiqué par l’Adobe ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) :


Pour créer un segment de ce type, 2 choix sʼoffrent à vous. Vous devez invariablement passer par le [Créateur de segments](/help/components/segmentation/segmentation-workflow/seg-build.md) dans Adobe Analytics, où dʼautres instructions sont disponibles.

* Dans le rail de gauche, cliquez sur le signe plus (+) en regard de [!UICONTROL Segments] :

![](assets/create-seg.png)

ou

* Accédez à [!UICONTROL Composants] > [!UICONTROL Segments], puis cliquez sur [!UICONTROL + Ajouter].


### Autres méthodes d’application de segments {#section_10FF2E309BA84618990EA5B473015894}


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Autres méthodes d’application de segments](https://video.tv.adobe.com/v/30994?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

Plusieurs autres méthodes permettent d’appliquer des segments à un projet d’analyse à structure libre.

| Action | Description |
|--- |--- |
| Création d’un segment d’après une sélection | Créez un segment incorporé. Ce segment s’applique uniquement au projet ouvert et n’est pas enregistré comme un segment Analytics. 1. Sélectionnez des lignes.  2. Cliquez avec le bouton de la souris sur la sélection.  3. Cliquez sur *Créer un segment d’après la sélection*. |
| Composants > Nouveau segment | Ouvre le créateur de segments. Voir [Créateur de segment](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=fr) pour en savoir plus sur la segmentation. |
| Partager > Partager le projet ou Partager > Traiter les données du projet | Dans l’outil [Traiter et partager](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=fr#concept_4A9726927E7C44AFA260E2BB2721AFC6), découvrez comment les segments que vous appliquez au projet sont disponibles dans l’analyse partagée avec le destinataire. |
| Utilisation de segments comme des dimensions | Vidéo : [Utilisation de segments comme dimensions dans Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-segments-as-dimensions-in-analysis-workspace.html?lang=fr) |

## Segment IQ

Segment IQ (également appelé Comparaison de segments) comprend les fonctionnalités suivantes :

* [Panneau de comparaison des segments :](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) fonctionnalité principale de Segment IQ. Faites glisser deux segments dans le panneau et affichez un rapport complet qui montre les différences les plus importantes sur le plan statistique et le chevauchement entre les deux audiences.
* [Comparaison des segments dans la visualisation Abandons :](/help/analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.md) découvrez comment différentes audiences se comparent les unes aux autres dans le contexte d’une visualisation Abandons.

## Plus d’informations

Pour une discussion approfondie sur la segmentation dans Adobe Analytics, rendez-vous [ici](/help/components/segmentation/seg-overview.md).
