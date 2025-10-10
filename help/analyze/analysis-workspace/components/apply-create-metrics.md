---
description: Découvrez les mesures et comment les utiliser dans Analysis Workspace.
title: Mesures
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 20%

---

# Mesures

Les mesures vous permettent de quantifier les points de données dans Analysis Workspace. Elles sont généralement utilisées comme colonnes dans une visualisation et liées aux dimensions.

## Utiliser des mesures dans Analysis Workspace

Les mesures sont flexibles dans leur utilisation dans Analysis Workspace. Faire glisser une mesure vers un tableau à structure libre vide pour afficher les tendances de cette mesure sur la période du projet. Vous pouvez également faire glisser une mesure lorsqu’une dimension est présente pour comparer cette mesure à chaque élément de dimension. Faire glisser une mesure au-dessus d’un en-tête de mesure existant la remplace et faire glisser une mesure près d’un en-tête permet d’afficher les deux côte à côte.

Pour plus d’informations sur l’ajout de mesures et d’autres types de composants à Analysis Workspace, voir [Utiliser des composants dans Analysis Workspace](use-components-in-workspace.md).

## Types de mesures

Adobe propose plusieurs types de mesures à utiliser dans Analysis Workspace :

* **Mesures standard** : la plupart des mesures que vous utilisez dans les projets sont des mesures standard. Exemples : [Pages vues](/help/components/metrics/page-views.md), [Revenu](/help/components/metrics/revenue.md)ou [Événements personnalisés](/help/components/metrics/custom-events.md). Pour plus d’informations, consultez la section [Vue d’ensemble des mesures](/help/components/metrics/overview.md) du guide d’utilisation des composants.

* **Mesures calculées** ![Calculateur](/help/assets/icons/Calculator.svg) : mesures définies par l’utilisateur ou l’utilisatrice et basées sur des mesures standard, des nombres statiques ou des fonctions algorithmiques. Les mesures calculées définies par l’utilisateur ou l’utilisatrice affichent une icône de calculateur dans la liste des composants disponibles. Pour plus d’informations, consultez la section [Vue d’ensemble des mesures calculées](/help/components/calculated-metrics/cm-overview.md) du guide d’utilisation des composants.

* **Modèles de mesures calculées** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) : mesures définies par Adobe qui se comportent de la même manière que les mesures calculées. Vous pouvez les utiliser tels quels dans les projets Workspace ou enregistrer une copie pour personnaliser sa logique. Les modèles de mesures calculées affichent une icône Adobe dans la liste des composants disponibles.

Vous pouvez voir si une mesure est approuvée ![icône Approuvée](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) ou non. Si vous souhaitez plus de détails sur une mesure, pointez sur la mesure, puis sélectionnez ![Icône Infos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg). Voir [Informations sur les composants](use-components-in-workspace.md#component-info) pour plus d’informations.


## Utilisation des mesures de dans Analysis Workspace

Les mesures peuvent être utilisées de différentes manières dans Analysis Workspace. Pour plus d’informations sur l’ajout de mesures et d’autres types de composants à Analysis Workspace, voir [Utiliser des composants dans Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Use metrics](https://video.tv.adobe.com/v/328563?quality=12&learn=on&captions=fre_fr){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

## Créer des mesures calculées

Les mesures calculées vous permettent de voir comment les mesures sont liées les unes aux autres, à l’aide d’opérateurs simples ou de fonctions statistiques.


Il existe plusieurs façons de créer des mesures calculées. La méthode que vous choisissez détermine si la mesure calculée est disponible dans la liste des composants de tous les projets ou uniquement dans le projet dans lequel elle a été créée.

### Création de mesures calculées pour tous les projets

Vous pouvez utiliser le [créateur de mesures calculées](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md) pour [créer des mesures calculées](/help/components/calculated-metrics/workflow/cm-workflow.md). Ainsi créées, les mesures calculées sont disponibles dans la liste des composants et peuvent être utilisées dans les projets de l’ensemble de votre organisation.


### Création de mesures calculées pour un seul projet

Vous pouvez rapidement créer une mesure calculée qui n’est disponible que pour le projet dans lequel elle a été créée.

Pour créer une mesure calculée pour un seul projet :

1. Dans Analysis Workspace, ouvrez le projet dans lequel vous souhaitez créer la mesure calculée.

1. Dans un tableau à structure libre, cliquez avec le bouton droit sur l’en-tête d’une colonne unique.

   Ou

   Sélectionnez deux colonnes tout en maintenant la touche Maj enfoncée, puis cliquez avec le bouton droit sur l’une des colonnes sélectionnées.

1. Sélectionnez **[!UICONTROL Créer une mesure à partir de la sélection]**

   Panneau ![Workspace mettant en surbrillance Créer à partir de la sélection](assets/create-metric-from-selection.png)

1. Pour créer une mesure calculée pour ce projet uniquement, choisissez l’une des options disponibles.

   Lorsqu’une seule colonne est sélectionnée, les options suivantes sont disponibles :

   * [!UICONTROL **Moyenne**] : crée une colonne qui affiche la valeur moyenne dans l’ensemble des éléments de dimension de la colonne. Les valeurs de colonne utilisent la fonction [Mean](/help/components/calculated-metrics/cm-reference/cm-functions.md#mean).

   * [!UICONTROL **Médiane**] : crée une colonne qui affiche la valeur médiane dans le jeu d’éléments de dimension de la colonne. Les valeurs de colonne utilisent la fonction [Médiane](/help/components/calculated-metrics/cm-reference/cm-functions.md#median).

   * [!UICONTROL **Colonne max**] : crée une colonne qui affiche la plus grande valeur de l’ensemble des éléments de dimension de la colonne. Les valeurs de colonne utilisent la fonction [Max. colonne](/help/components/calculated-metrics/cm-reference/cm-functions.md#column-maximum).

   * [!UICONTROL **Colonne min**] : crée une colonne qui affiche la plus petite valeur du jeu d’éléments de dimension pour la colonne. Les valeurs de colonne utilisent la fonction [Column Minimum](/help/components/calculated-metrics/cm-reference/cm-functions.md#column-minimum).

   * [!UICONTROL **Somme des colonnes**] : crée une colonne qui ajoute toutes les valeurs numériques d’une mesure dans une colonne (sur l’ensemble des éléments d’une dimension). Les valeurs de colonne utilisent la fonction [Column Sum](/help/components/calculated-metrics/cm-reference/cm-functions.md#column-sum).

   Lorsque deux colonnes sont sélectionnées, les options suivantes sont disponibles :

   * [!UICONTROL **Diviser**] : crée une colonne qui divise les valeurs des deux colonnes sélectionnées.

   * [!UICONTROL **Soustraire**] : crée une colonne qui soustrait les valeurs des deux colonnes sélectionnées.

   * [!UICONTROL **Ajouter**] : crée une colonne qui ajoute les valeurs des deux colonnes sélectionnées.

   * [!UICONTROL **Multiplier**] : crée une colonne qui multiplie les valeurs des deux colonnes sélectionnées.

   * [!UICONTROL **Changement en pourcentage**] : crée une colonne qui affiche le changement en pourcentage entre les deux colonnes sélectionnées.

[Mesures calculées : mesures sans implémentation](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics) (3:42)


## Comparaison de mesures avec différents modèles d’attribution

Pour comparer rapidement un modèle d’attribution à un autre, cliquez avec le bouton droit sur une mesure et sélectionnez **[!UICONTROL Comparer les modèles d’attribution]** :

![Comparer l’attribution](assets/compare-attribution.png)

Ce raccourci vous permet de comparer un modèle d’attribution à un autre sans faire glisser une mesure et la configurer deux fois.

## Utilisation de la fonction [!UICONTROL moyenne cumulée] pour appliquer le lissage des mesures

Regardez une vidéo sur ce sujet :


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Moyenne cumulée](https://video.tv.adobe.com/v/35044?quality=12&learn=on&captions=fre_fr){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

