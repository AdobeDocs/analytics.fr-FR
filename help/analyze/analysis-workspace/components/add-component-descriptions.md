---
description: Découvrez comment les administrateurs et administratrices peuvent ajouter des descriptions aux composants à l’aide d’une suite de rapports ou du dictionnaire de données.
title: Ajouter des descriptions des composants
feature: Components
role: Admin
exl-id: db36ee4a-66e2-45d1-8b7a-49570b5fce93
TQID: https://experienceleague.adobe.com/8z9vnSfrxEb1nkOlTTlHrp3BdElFJmTjbsSLBGbE7Gs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: c45e2849-b5ab-4ac6-8df1-bbe34c2dd79e
    internal-label: Data Dictionary
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b3d9fb81837398b349496ec261dc1d0ba3df3645
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 20%
---
# Ajouter des descriptions des composants

Les descriptions permettent aux utilisateurs et utilisatrices de savoir comment utiliser au mieux les différents composants lors de la création de projets dans Analysis Workspace ou lors de l’affichage de rapports.

Les administrateurs et administratrices d’Analytics peuvent ajouter des descriptions pour les composants (dimensions, mesures, segments et périodes) dans une suite de rapports ou à l’aide du dictionnaire de données directement dans Analysis Workspace.

## Suite de rapports

Vous pouvez ajouter des descriptions aux composants dans une suite de rapports.

1. Sélectionnez **[!UICONTROL Admin]** > **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Suites de rapports]**.
1. Dans le Gestionnaire de suites de rapports, sélectionnez la suite de rapports pour laquelle vous souhaitez fournir des descriptions de composant.
1. Sélectionnez **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Conversion]** > **[!UICONTROL Variables de conversion]**.
1. Sélectionnez ![Ajouter](/help/assets/icons/Add.svg) pour afficher les détails d’une variable de conversion.
1. Cochez la case correspondant à **[!UICONTROL Description]** et ajoutez une description.
1. Répétez les étapes 4 et 5 pour toute autre variable à laquelle vous souhaitez ajouter une description.
1. Sélectionnez **[!UICONTROL Enregistrer]**.

>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Ajouter des descriptions de composant](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/intro-to-analytics/customizing-the-ui/adding-dimension-and-metric-descriptions){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Dictionnaire de données {#add-descriptions}

Le dictionnaire de données d’Analysis Workspace aide les utilisateurs et utilisatrices, ainsi que les administrateurs et administratrices, à suivre plus facilement les composants de leur environnement Analytics et à mieux les comprendre. Le dictionnaire de données permet aux administrateurs et administratrices d’Analytics d’ajouter des descriptions des composants directement dans Analysis Workspace.

Pour plus d’informations sur la modification d’une description de composant dans le dictionnaire de données, voir [Modifier les entrées de composant dans le dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).

Pour obtenir des informations générales sur le dictionnaire de données, voir [Vue d’ensemble du dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).

>[!MORELIKETHIS]
>
>[Paramètres des composants : rapport](/help/components/vrs/vrs-components.md)
>[Entrées du composant Dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md)
>

## Génération automatique de descriptions

{{release-limited-testing-section}}

Au lieu d’écrire chaque description manuellement, Adobe Analytics peut utiliser l’IA générative pour écrire des descriptions pour vous. Vous pouvez générer une description pour un seul composant ou générer des descriptions pour de nombreux composants en même temps.

Descriptions générées :

* Ne contiennent pas plus de 3 phrases.
* Terminez par le texte **[!UICONTROL Généré par Adobe à l’aide de l’IA]** afin que les utilisateurs et utilisatrices sachent que la description a été générée.
* Modifiables une fois qu’ils ont été générés.

### Conditions préalables

Avant de pouvoir générer des descriptions, votre entreprise doit accepter certains termes juridiques d’IA générative. Si votre entreprise n’a pas accepté ces conditions, l’option permettant de générer des descriptions est grisée. Sélectionnez l’icône d’information ![Infos](/help/assets/icons/InfoOutline.svg) en regard de l’option pour savoir comment activer la fonctionnalité, ou contactez l’administrateur ou l’administratrice de votre organisation ou l’équipe du compte Adobe.

### Comment sont générées les descriptions ?

Les descriptions générées sont basées sur la définition du composant et sur le contexte supplémentaire relatif à l’utilisation du composant dans votre suite de rapports, telles que :

* Éléments principaux d’une dimension
* Composants fréquemment utilisés avec le composant

Lorsqu’une mesure calculée ou un segment fait référence à un autre segment, la description générée explique la définition du segment référencé.

### Générer des descriptions à partir de divers emplacements

Vous pouvez générer des descriptions dans les zones suivantes d’Adobe Analytics. Certains emplacements vous permettent de générer des descriptions pour plusieurs composants, d’autres non.

Sélectionnez un emplacement pour savoir comment y générer des descriptions.

| Emplacement | Composants pris en charge | Un seul composant | Composants multiples |
| --- | --- | --- | --- |
| [Dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md) | <ul><li>Dimensions</li><li>Mesures</li><li>Mesures calculées</li><li>Segments</li><li>Périodes</li></ul> | Oui | Oui |
| [Créateur de segments](/help/components/segmentation/segmentation-workflow/seg-build.md) | Segments | Oui | Non |
| [ Gestionnaire de segments ](/help/components/segmentation/segmentation-workflow/seg-manage.md#action-bar) | Segments | Non | Oui |
| [Créateur de mesures calculées](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md) | Mesures calculées | Oui | Non |
| [Gestionnaire de mesures calculées](/help/components/calculated-metrics/workflow/cm-manager.md#action-bar) | Mesures calculées | Non | Oui |
| [Créateur de périodes](/help/analyze/analysis-workspace/components/calendar-date-ranges/create.md#date-range-builder) | Périodes | Oui | Non |
| [Gestionnaire de périodes](/help/analyze/analysis-workspace/components/calendar-date-ranges/manage.md#action-bar) | Périodes | Non | Oui |

{style="table-layout:auto"}