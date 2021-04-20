---
description: 'Les composants d’Analysis Workspace se composent de dimensions, de mesures, de segments et de plages de dates que vous pouvez faire glisser sur un projet. '
title: Aperçu des composants
feature: Workspace Basics
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 17%

---


# Aperçu des composants

Les composants d’Analysis Workspace se composent de dimensions, de mesures, de segments et de plages de dates que vous pouvez faire glisser sur un projet.

Pour accéder au menu Composants, cliquez sur l&#39;icône **[!UICONTROL Composants]** dans le rail de gauche. Vous pouvez basculer entre les [panneaux](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=fr-FR), [Visualisations](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) et les composants à partir des icônes du rail de gauche ou en utilisant [touches d&#39;accès rapide](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/component-overview.png)

Vous pouvez également ajuster les [paramètres de densité de Vue](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) du projet pour afficher plus de valeurs dans le rail de gauche en même temps en accédant à **[!UICONTROL Projet > Informations et paramètres du projet > Densité de la Vue]**.

## Dimensions {#dimensions}

[**Les**](https://docs.adobe.com/content/help/en/analytics/components/dimensions/overview.html) dimensions sont des attributs de texte qui décrivent votre comportement de visiteur et peuvent être affichés, ventilés et comparés dans votre analyse. Ils se trouvent dans le rail Composant de gauche (section orange) et sont généralement appliqués en tant que lignes d’un tableau.

Parmi les exemples de dimensions, citons [!UICONTROL Nom de page], [!UICONTROL Canaux marketing], [!UICONTROL Type de périphérique] et [!UICONTROL Produits]. Les Dimensions sont fournies par Adobe et sont capturées par votre implémentation personnalisée (eVar, props, classifications, etc.).

Chaque dimension contient également **des éléments de dimension**. Les éléments de Dimension se trouvent dans le rail de composant de gauche en cliquant sur la flèche de droite en regard de n’importe quel nom de dimension (les éléments sont jaunes).

Parmi les exemples d&#39;éléments de dimension, citons [!UICONTROL Page d&#39;accueil] (dans la dimension [!UICONTROL Page]), [!UICONTROL Recherche payante] (dans la dimension [!UICONTROL Canal marketing]), [!UICONTROL Tablette] (dans le [!UICONTROL Type de périphérique mobile] > dimension), etc.

![](assets/dimensions.png)

## Mesures {#metrics}

[**Les**](https://docs.adobe.com/content/help/en/analytics/components/metrics/overview.html) mesures sont des mesures quantitatives sur le comportement des visiteurs. Ils se trouvent dans le rail de composants de gauche (section verte) et sont généralement appliqués en tant que colonnes d’un tableau.

Parmi les exemples de mesures, citons [!UICONTROL vues de page], [!UICONTROL Visites], [!UICONTROL Commandes], [!UICONTROL Durée moyenne de consultation] et [!UICONTROL Recettes/Commande]. Les mesures sont fournies par Adobe ou capturées via votre implémentation personnalisée ([!UICONTROL événements de réussite]), ou créées à l’aide du [créateur de mesures calculées](https://docs.adobe.com/content/help/fr-FR/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html).

![](assets/metrics.png)

## Segments {#segments}

[**Les**](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) segments sont des filtres d’audience appliqués à votre analyse. Ils se trouvent dans le rail de composants de gauche (section bleue) et sont généralement appliqués en haut d’un panneau ou au-dessus des colonnes de mesures dans un tableau.

Parmi les exemples de segments, citons [!UICONTROL Visiteurs de périphériques mobiles], [!UICONTROL Visites à partir d’un courrier électronique] et [!UICONTROL Accès authentifiés]. Les segments sont fournis par Adobe, ou créés dans la zone de dépôt du panneau [a1/>, ou créés à l’aide du [créateur de segments](https://docs.adobe.com/content/help/fr-FR/analytics/components/segmentation/segmentation-workflow/seg-build.html).](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)

![](assets/segments.png)

## Périodes {#date-ranges}

[**Les**](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) plages de dates correspondent à la plage de dates à laquelle vous effectuez votre analyse. Ils se trouvent dans le rail de composant de gauche (section violet) et sont généralement appliqués dans le calendrier de chaque panneau.

Voici quelques exemples de plages de dates : juillet 2019, [!UICONTROL 4 dernières semaines] et [!UICONTROL Ce mois]. Les plages de dates sont fournies par Adobe, appliquées dans le [calendrier du panneau](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html) ou créées à l’aide du [créateur de plages de dates](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html).

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

Les composants personnalisés peuvent également être gérés par l’intermédiaire de leurs gestionnaires de composants respectifs. Par exemple, [Gestionnaire de segments](/help/components/segmentation/segmentation-workflow/seg-manage.md).
