---
description: valeur nulle
title: Créateur d’informations rapide
translation-type: tm+mt
source-git-commit: 77b126b2add78113c266265f413240f27f89bced

---


# Créateur d’informations rapide

>[!IMPORTANT]
>
>Quick Insights est actuellement en phase de test bêta et n’est pas encore disponible pour tous les clients d’Adobe Analytics.

Quick Insights fournit des conseils aux non-analystes et aux nouveaux utilisateurs de   Workspace pour apprendre à répondre rapidement et facilement aux questions de l’entreprise. C&#39;est aussi un outil idéal pour les utilisateurs expérimentés qui veulent répondre rapidement à une question sans avoir à construire eux-mêmes un tableau.

Lorsque vous pour la première fois à l’aide de cet  Espace de travail , vous pouvez vous demander quelles visualisations seraient les plus utiles, quelles dimensions et mesures pourraient faciliter les informations, où faire glisser et déposer des éléments, où créer un segment, etc.

Pour vous aider à cela, en vous basant sur votre propre  l’utilisation des composants de données dans  Espace de travail, Quick Insights utilise un algorithme qui vous présente les dimensions, mesures, segments et plages de dates les plus populaires que vosutilisateurs utilisent.

Quick Insights vous aide à

* Créez correctement un tableau de données et la visualisation qui l’accompagne dans   Workspace.
* Découvrez la terminologie et le vocabulaire des composants de base et des éléments de  de  Workspace.
* Effectuez des ventilations simples de dimensions, ajoutez plusieurs mesures ou comparez facilement des segments dans un tableau à structure libre.
* Modifiez ou testez divers types de visualisation pour trouver rapidement et intuitivement l&#39;outil de recherche pour vos  .

## Terminologie clé de base

Voici quelques-uns des termes de base que vous devez connaître. Chaque tableau de données se compose de deux blocs fonctionnels ou plus que vous utilisez pour raconter l’histoire de vos données.

| Bloc de création | Définition |
|---|---|
| Dimension | Les dimensions sont des descriptions ou des caractéristiques des données de mesure qui peuvent être visualisées, ventilées et comparées dans un projet. Il s’agit de valeurs et de dates non numériques qui se répartissent en éléments de dimension. Par exemple, &quot;browser&quot; ou &quot;page&quot; sont des dimensions. |
| Elément de dimension | Les éléments de dimension sont des valeurs individuelles pour une dimension. Par exemple, les éléments de dimension de la dimension de navigateur seraient &quot;Chrome&quot;, &quot;Firefox&quot;, &quot;Edge&quot;, etc. |
| Mesure | Les mesures sont des informations quantitatives sur les  de  du, telles que les, les clics publicitaires, les rechargements, la durée moyenne de consultation, les unités, les commandes, les recettes, etc. |
| Visualisation | Workspace  de plusieurs visualisations [pour créer des représentations](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md) visuelles de vos données. |
| Segment | Les segments vous permettent d’identifier des sous-ensembles de en fonction de caractéristiques ou d’interactions sur le site Web. Par exemple, vous pouvez créer des segments de basés sur des attributs : type de navigateur, périphérique, nombre de visites, pays, sexe ou en fonction des interactions : campagnes, recherche de mots-clés, moteur de recherche ou en fonction des sorties et des entrées : de Facebook, d’un défini, d’un domaine référent ou d’après des variables personnalisées : champ de formulaire,  défini, ID de client. |

## Prise en main de Quick Insights

1. Connectez-vous à Adobe Analytics à l’aide des informations d’identification qui vous ont été fournies.
1. Accédez à [!UICONTROL Workspace] et cliquez **[!UICONTROL Create New Project]** , puis cliquez **[!UICONTROL Quick Insights Builder]**.

   ![](assets/qibuilder.png)

1. Lorsque vous , passez en revue le court didacticiel qui vous apprend quelques-unes des bases de Quick Insight Builder. Ou cliquez sur pour **[!UICONTROL Skip Tutorial]**.
1. Sélectionnez vos blocs de création (également appelés composants) : dimensions (orange), mesures (vert), segments (bleu) ou plages de dates (violet) Vous devez sélectionner au moins une dimension et une mesure pour qu’un tableau soit créé automatiquement.

   ![](assets/qibuilder2.png)

   Vous pouvez sélectionner les blocs de création de trois manières différentes :
   * Faites-les glisser à partir du rail de gauche.
   * Si vous savez ce que vous recherchez : Le  taper le nom et les informations rapides compléteront les blancs pour vous.
   * Cliquez sur la liste déroulante et recherchez le 

1. Lorsque vous avez ajouté au moins une dimension et une mesure, les éléments suivants sont créés pour vous :

   * Tableau à structure libre avec la dimension à gauche (verticale) et la ou les mesures en haut (horizontale). Consultez ce tableau :

1. (Facultatif) Recherchez les dimensions et affichez les éléments de dimension en cliquant sur la flèche > Droite en regard de la dimension.



## Limites connues

Si vous tentez de modifier directement le tableau, le créateur de Quick Insight (l’outil de remplissage du blanc) ne sera plus synchronisé. Vous pouvez restaurer les paramètres de Quick Insight précédents, mais si ce n’est pas le cas, la création directe entraîne le comportement du tableau en tant que tableau à structure libre classique.

