---
description: 'Les composants d’Analysis Workspace se composent de dimensions, de mesures, de segments et de plages de dates que vous pouvez faire glisser sur un projet. '
title: Aperçu des composants
translation-type: tm+mt
source-git-commit: a290e5790591d73c397b2eb99f0c070e0ea71b10
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 13%

---


# Aperçu des composants

Les composants d’Analysis Workspace se composent de dimensions, de mesures, de segments et de plages de dates que vous pouvez faire glisser sur un projet.

To access the Components menu, click the **[!UICONTROL Components]** icon in the left rail. Vous pouvez permuter entre [Panneaux](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html), [Visualisations](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)et Composants à partir des icônes du rail de gauche ou en utilisant des [touches d’accès rapide](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/component-overview.png)

Vous pouvez également ajuster les paramètres [de densité de](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) Vue du projet pour afficher d’autres valeurs simultanément dans le rail de gauche en accédant à **[!UICONTROL Projet > Informations et paramètres du projet > Densité]** de la Vue.

## Dimensions {#dimensions}

[**Les Dimensions**](https://docs.adobe.com/content/help/en/analytics/components/dimensions/overview.html) sont des attributs de texte qui décrivent votre comportement de visiteur et peuvent être visualisés, ventilés et comparés dans votre analyse. Ils se trouvent dans le rail Composant de gauche (section orange) et sont généralement appliqués en tant que lignes d’un tableau.

Parmi les exemples de dimensions, citons [!UICONTROL Page Name], [!UICONTROL Marketing Canaux], [!UICONTROL Device Type]et [!UICONTROL Products. ] Les Dimensions sont fournies par Adobe et sont capturées par votre implémentation personnalisée (eVar, props, classifications, etc.).

Chaque dimension contient également des éléments **de** dimension. Les éléments de Dimension se trouvent dans le rail de composant de gauche en cliquant sur la flèche de droite en regard de n’importe quel nom de dimension (les éléments sont jaunes).

Parmi les exemples d’éléments de dimension, citons [!UICONTROL la page d’accueil] (dans la dimension [!UICONTROL Page] ), la recherche  payante (dans la dimension Canal [!UICONTROL marketing), Tablet (dans la dimension  de type de périphérique mobile), etc.]

![](assets/dimensions.png)

## Mesures {#metrics}

[**Les mesures**](https://docs.adobe.com/content/help/en/analytics/components/metrics/overview.html) sont des mesures quantitatives du comportement des visiteurs. Ils se trouvent dans le rail de composants de gauche (section verte) et sont généralement appliqués en tant que colonnes d’un tableau.

Parmi les exemples de mesures, citons [ ! UICONTROL Page vues, [!UICONTROL Visites], [!UICONTROL Commandes], Durée [!UICONTROL moyenne de consultation]et [!UICONTROL Recettes/Commande. ] Les mesures sont fournies par Adobe, ou capturées via votre implémentation personnalisée (événements[!UICONTROL de]réussite), ou créées à l’aide du créateur de mesures [calculées](https://docs.adobe.com/content/help/fr-FR/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html).

![](assets/metrics.png)

## Segments {#segments}

[**Les segments**](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) sont des filtres d’audience appliqués à votre analyse. Ils se trouvent dans le rail de composants de gauche (section bleue) et sont généralement appliqués en haut d’un panneau ou au-dessus des colonnes de mesures dans un tableau.

Parmi les exemples de segments, citons les Visiteurs [!UICONTROL de périphériques]mobiles, les [!UICONTROL visites à partir du courrier électronique]et les accès authentifiés. Les segments sont fournis par Adobe, créés dans la zone de dépôt [du](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)panneau ou créés à l’aide du créateur [de](https://docs.adobe.com/content/help/fr-FR/analytics/components/segmentation/segmentation-workflow/seg-build.html)segments.

![](assets/segments.png)

## Périodes {#date-ranges}

[**Les plages**](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) de dates sont la plage de dates à laquelle vous effectuez votre analyse. Ils se trouvent dans le rail de composant de gauche (section violet) et sont généralement appliqués dans le calendrier de chaque panneau.

Parmi les exemples de plages de dates, citons juillet 2019, [!UICONTROL 4 dernières semaines]et [!UICONTROL Ce mois]. Les plages de dates sont fournies par Adobe, appliquées dans le calendrier [du](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)panneau ou créées à l’aide du créateur [de plages de](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html)dates.

![](assets/date-ranges.png)

## Actions des composants {#actions}

Vous pouvez gérer les composants (individuellement ou en sélectionnant plusieurs) directement dans le rail de gauche. Cliquez avec le bouton droit de la souris sur un composant ou cliquez sur l’icône Point d’action située en haut de la liste de composant.

![](assets/component-actions.png)

| Action des composants | Description |
|--- |--- |
| Baliser | Organisez ou gérez les composants en leur appliquant des balises. Vous pouvez ensuite effectuer une recherche par balise dans le rail de gauche en cliquant sur le filtre ou en saisissant #. Les balises agissent également en tant que filtres dans les gestionnaires de composants. |
| Favori | Ajoutez le composant à votre liste de favoris. Comme les balises, vous pouvez effectuer des recherches par Favoris dans le rail de gauche et filtrer par eux dans les gestionnaires de composants. |
| Approuver | Marquez les composants comme Approuvés pour signaler à vos utilisateurs que le composant est approuvé par l’organisation. Comme les balises, vous pouvez effectuer une recherche par Approuvé dans le rail de gauche et filtrer par elles dans les gestionnaires de composants. |
| Partager | Partagez des composants avec des utilisateurs de votre entreprise. Cette option est disponible uniquement pour les composants personnalisés, tels que les segments ou les mesures calculées. |
| Supprimer | Supprimez les composants dont vous n’avez plus besoin. Cette option est disponible uniquement pour les composants personnalisés, tels que les segments ou les mesures calculées. |

Les composants personnalisés peuvent également être gérés par l’intermédiaire de leurs gestionnaires de composants respectifs. Par exemple, le Gestionnaire [de](/help/components/segmentation/segmentation-workflow/seg-manage.md)segments.
