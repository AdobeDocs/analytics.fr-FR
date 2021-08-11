---
description: 'Les composants d’Analysis Workspace sont constitués des dimensions, mesures, segments et périodes que vous pouvez glisser-déposer dans un projet. '
title: Aperçu des composants
feature: Concepts de base de Workspace
role: User, Admin
exl-id: e2c98c77-64ee-4349-956a-3ab092e36017
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: ht
source-wordcount: '715'
ht-degree: 100%

---

# Aperçu des composants

Les composants d’Analysis Workspace sont constitués des dimensions, mesures, segments et périodes que vous pouvez glisser-déposer dans un projet.

Pour accéder au menu des composants, cliquez sur l’icône **[!UICONTROL Composants]** dans le rail de gauche. Vous pouvez basculer entre les [Panneaux](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=fr), les [Visualisations](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=fr) et les composants à partir des icônes du rail de gauche ou en utilisant les [touches de raccourcis](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/component-overview.png)

Vous pouvez également régler les [paramètres d’affichage de la densité](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=fr) du projet pour afficher plus de valeurs en même temps dans le rail de gauche en allant dans **[!UICONTROL Projet > Informations et paramètres du projet > Affichage de la densité]**.

## Dimensions {#dimensions}

Les [**dimensions**](https://experienceleague.adobe.com/docs/analytics/components/dimensions/overview.html?lang=fr) sont des attributs textuels qui décrivent le comportement du visiteur. Elles peuvent être affichées, divisées et comparées dans votre analyse. Elles se trouvent dans le rail des composants de gauche (section orange) et sont généralement appliquées sous forme de lignes d’un tableau.

Parmi les exemples de dimensions, citons notamment [!UICONTROL Nom de page], [!UICONTROL Canaux marketing], [!UICONTROL Type d’appareil] et [!UICONTROL Produits]. Les dimensions sont fournies par Adobe et sont capturées par le biais de votre implémentation personnalisée (eVar, props, classifications et bien d’autres).

Chaque dimension contient également des **éléments de dimension**. Les éléments de dimension se trouvent dans le rail des composants de gauche. Vous pouvez y accéder en cliquant sur la flèche de droite en regard de n’importe quel nom de dimension (les éléments sont jaunes).

Parmi les exemples d’éléments de dimension, citons notamment [!UICONTROL Page d’accueil] (dans la dimension [!UICONTROL Page]), [!UICONTROL Référencement payant] (dans la dimension [!UICONTROL Canal marketing]), [!UICONTROL Tablette] (dans la dimension [!UICONTROL Type de périphérique mobile]), etc.

![](assets/dimensions.png)

## Mesures {#metrics}

Les [**mesures**](https://experienceleague.adobe.com/docs/analytics/components/metrics/overview.html?lang=fr) sont des mesures quantitatives relatives au comportement des visiteurs. Elles se trouvent dans le rail des composants de gauche (section verte) et sont généralement appliquées sous forme de colonnes d’un tableau.

Parmi les exemples de mesures, citons notamment [!UICONTROL Pages vues], [!UICONTROL Visites], [!UICONTROL Commandes], [!UICONTROL Durée moyenne de la visite] et [!UICONTROL Recettes/Commande]. Les mesures sont fournies par Adobe ou capturées par le biais de votre implémentation personnalisée ([!UICONTROL Événements de succès]). Elles peuvent également être créées à l’aide du [créateur de mesures calculées](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=fr).

![](assets/metrics.png)

## Segments {#segments}

Les [**segments**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html?lang=fr) sont des filtres d’audience appliqués à votre analyse. Ils se trouvent dans le rail des composants de gauche (section bleue) et sont généralement appliqués en haut d’un panneau ou au-dessus des colonnes de mesures dans un tableau.

Parmi les exemples de segments, citons notamment [!UICONTROL Visiteurs d’appareils mobiles], [!UICONTROL Visites à partir d’un e-mail] et [!UICONTROL Accès authentifiés]. Les segments sont fournis par Adobe ou créés dans la [zone de dépôt du panneau](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=fr). Ils peuvent également être créés à l’aide du [créateur de segments](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=fr).

![](assets/segments.png)

## Périodes {#date-ranges}

Les [**périodes**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html?lang=fr) sont les plages de dates dans lesquelles vous effectuez votre analyse. Elles se trouvent dans le rail des composants de gauche (section violette) et sont généralement appliquées dans le calendrier de chaque panneau.

Parmi les exemples de périodes, citons notamment juillet 2019, [!UICONTROL 4 dernières semaines] et [!UICONTROL Ce mois-ci]. Les périodes sont fournies par Adobe, appliquées dans le [calendrier du panneau](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=fr) ou créées à l’aide du [créateur de périodes](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=fr).

![](assets/date-ranges.png)

## Actions des composants {#actions}

Vous pouvez gérer les composants directement dans le rail de gauche, soit de manière individuelle, soit en en sélectionnant plusieurs. Faites un clic droit sur un composant ou cliquez sur l’icône de points d’action en haut de la liste des composants.

![](assets/component-actions.png)

| Action des composants | Description |
|--- |--- |
| Baliser | Organisez ou gérez les composants en leur appliquant des balises. Vous pouvez ensuite effectuer une recherche par balise dans le rail de gauche en cliquant sur le filtre ou en saisissant #. Les balises servent également de filtres dans les gestionnaires de composants. |
| Favori | Ajoutez le composant à votre liste de favoris. Comme avec les balises, vous pouvez effectuer une recherche par Favoris dans le rail de gauche et les utiliser comme filtre dans les gestionnaires de composants. |
| Approuver | Marquez les composants comme Approuvés pour signaler à vos utilisateurs que le composant est approuvé par l’organisation. Comme avec les balises, vous pouvez effectuer une recherche par composants Approuvés dans le rail de gauche et les utiliser comme filtre dans les gestionnaires de composants. |
| Partager | Partagez des composants avec des utilisateurs de votre organisation. Cette option est uniquement disponible pour les composants personnalisés, tels que les segments ou les mesures calculées. |
| Supprimer | Supprimez les composants dont vous n’avez plus besoin. Cette option est uniquement disponible pour les composants personnalisés, tels que les segments ou les mesures calculées. |

Les composants personnalisés peuvent également être gérés par l’intermédiaire de leurs gestionnaires de composants respectifs. Par exemple, le [Gestionnaire de segments](/help/components/segmentation/segmentation-workflow/seg-manage.md).
