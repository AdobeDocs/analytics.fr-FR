---
description: Quick Insights Builder est un outil destiné aux nouveaux utilisateurs de Workspace qui les guide dans la création de tableaux de données et de visualisations.
title: Créateur de rapports rapides
translation-type: tm+mt
source-git-commit: 6eda9e3e5bd450213253a8181042c24c318c0300

---


# Créateur de rapports rapides

>[!IMPORTANT]
>
>**[!UICONTROL Quick Insights]** est actuellement en phase de test bêta et n’est pas encore disponible pour tous les clients d’Adobe Analytics.

[!UICONTROL Quick Insights] fournit des conseils aux non-analystes et aux nouveaux utilisateurs d’ [!UICONTROL Analysis Workspace] apprendre à répondre rapidement et facilement aux questions de l’entreprise. C&#39;est aussi un outil idéal pour les utilisateurs expérimentés qui veulent répondre rapidement à une question sans avoir à construire eux-mêmes un tableau.

Lorsque vous  d’utiliser cette [!UICONTROL Analysis Workspace]méthode pour la première fois, vous pouvez vous demander quelles visualisations seraient les plus utiles, quelles dimensions et mesures pourraient faciliter les informations, où faire glisser des éléments, où créer un segment, etc.

Pour vous aider à cela, et en fonction de votre propre  l’utilisation des composants de données dans [!UICONTROL Analysis Workspace], [!UICONTROL Quick Insights] utilisez un algorithme qui vous présentera les dimensions, mesures, segments et plages de dates les plus populaires que vos  utilisent.

[!UICONTROL Quick Insights] vous aide

* Créez correctement un tableau de données et la visualisation qui l’accompagne dans [!UICONTROL Analysis Workspace].
* Apprenez la terminologie et le vocabulaire pour les composants de base et les pièces de [!UICONTROL Analysis Workspace]base.
* Réalisez des ventilations simples de dimensions, ajoutez plusieurs mesures ou comparez facilement des segments au sein d’un même [!UICONTROL Freeform table]groupe.
* Modifiez ou testez divers types de visualisation pour trouver rapidement et intuitivement l&#39;outil de recherche pour vos  .

## Terminologie clé de base

Voici quelques-uns des termes de base que vous devez connaître. Chaque tableau de données se compose de deux blocs fonctionnels (composants) ou plus que vous utilisez pour raconter l’histoire de vos données.

| Bloc de création (composant) | Définition |
|---|---|
| [!UICONTROL Dimension] | Les dimensions sont des descriptions ou des caractéristiques des données de mesure qui peuvent être visualisées, ventilées et comparées dans un projet. Il s’agit de valeurs et de dates non numériques qui se répartissent en éléments de dimension. Par exemple, &quot;browser&quot; ou &quot;page&quot; sont des dimensions. |
| [!UICONTROL Dimension item] | Les éléments de dimension sont des valeurs individuelles pour une dimension. Par exemple, les éléments de dimension de la dimension de navigateur seraient &quot;Chrome&quot;, &quot;Firefox&quot;, &quot;Edge&quot;, etc. |
| [!UICONTROL Metric] | Les mesures sont des informations quantitatives sur les  de  du, telles que les, les clics publicitaires, les rechargements, la durée moyenne de consultation, les unités, les commandes, les recettes, etc. |
| [!UICONTROL Visualization] | Workspace  un certain nombre de visualisations [](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md) pour créer des représentations visuelles de vos données, telles que des graphiques à barres, des diagrammes en anneau, des histogrammes, des diagrammes en courbes, des cartes, des diagrammes en dispersion, etc. |
| [!UICONTROL Breakdown] | Une ventilation permet de ventiler littéralement une dimension selon d’autres dimensions. Dans notre exemple, vous pouvez ventiler les États américains par Périphériques mobiles pour obtenir les visites par état, ou par types de périphériques mobiles, ou par régions, par Campagnes internes, etc. |
| [!UICONTROL Segment] | Les segments vous permettent d’identifier des sous-ensembles de en fonction de caractéristiques ou d’interactions sur le site Web. Vous pouvez, par exemple, créer [!UICONTROL Visitor] des segments en fonction d’attributs : type de navigateur, périphérique, nombre de visites, pays, sexe ou en fonction des interactions : campagnes, recherche de mots-clés, moteur de recherche ou en fonction des sorties et des entrées : de Facebook, d’un défini, d’un domaine référent ou d’après des variables personnalisées : champ de formulaire,  défini, ID de client. |

## Prise en main de Quick Insights

1. Connectez-vous à Adobe Analytics à l’aide des informations d’identification qui vous ont été fournies.
1. Accédez à [!UICONTROL Workspace] et cliquez **[!UICONTROL Create New Project]** , puis cliquez **[!UICONTROL Quick Insights Builder]**.

   ![](assets/qibuilder.png)

1. Lorsque vous , passez d&#39;abord par le court tutoriel qui vous apprend quelques-uns des [!UICONTROL Quick Insights Builder] principes de base. Ou cliquez sur pour **[!UICONTROL Skip Tutorial]**.
1. Sélectionnez vos blocs de création (également appelés composants) : dimensions (orange), mesures (vert), segments (bleu) ou plages de dates (violet) Vous devez sélectionner au moins une dimension et une mesure pour qu’un tableau soit créé automatiquement.

   ![](assets/qibuilder2.png)

   Vous pouvez sélectionner les blocs de création de trois manières différentes :
   * Faites-les glisser à partir du rail gauche.
   * Si vous savez ce que vous recherchez :  taper le nom et vous [!UICONTROL Quick Insights Builder] renseignez les champs vides.
   * Cliquez sur la liste déroulante et recherchez le .

1. Lorsque vous avez ajouté au moins une dimension et une mesure, les éléments suivants sont créés pour vous :

   * Tableau à structure libre avec la dimension (ici, Etats-Unis) verticalement et la mesure (ici, Visites) horizontalement en haut. Consultez ce tableau :
   ![](assets/qibuilder3.png)

   * Visualisation connexe, dans ce cas un graphique à [barres](/help/analyze/analysis-workspace/visualizations/bar.md). La visualisation qui est générée dépend du type de données que vous avez ajoutées au tableau. Vous pouvez modifier le type de visualisation en cliquant sur la flèche déroulante en regard de **[!UICONTROL Bar]**.


1. (Facultatif) Recherchez les dimensions et affichez les éléments de dimension en cliquant sur la flèche > Droite en regard de la dimension.

1. Essayez d’ajouter d’autres améliorations comme décrit ci-dessous sous &quot;Autres options utiles&quot;.

## Autres options utiles

D’autres conseils utiles s’affichent dans le [!UICONTROL Quick Insights Builder], dont certains selon votre dernière action.

* **Essayez de faire glisser**: Si, par exemple, vous avez utilisé la liste déroulante pour sélectionner votre bloc de création, cela peut s’afficher :

   ![](assets/qibuilder4.png)

* **Modifiez votre visualisation**: vous encourage à essayer différentes représentations visuelles de vos données jusqu&#39;à ce que vous trouviez celle qui brille vraiment. Voici un exemple de graphique linéaire :

   ![](assets/qibuilder8.png)

* **Ventilation par**: Vous pouvez utiliser jusqu’à 3 niveaux de ventilations sur les dimensions pour analyser les données dont vous avez vraiment besoin.

   ![](assets/qibuilder5.png)

* **Ajouter d’autres mesures**: Vous pouvez ajouter jusqu’à 2 autres mesures à l’aide de l’opérateur ET pour les ajouter au tableau.

   ![](assets/qibuilder6.png)

* **Ajouter d’autres segments**: Vous pouvez ajouter jusqu’à 2 segments supplémentaires en utilisant les opérateurs ET ou OU pour les ajouter au tableau. Regardez ce qui arrive au tableau lorsque vous ajoutez des utilisateurs mobiles OU des fidèles. Ils sont les uns à côté des autres, au-dessus des mesures. Si vous ajoutez des utilisateurs mobiles ET des fidèles, les résultats des deux segments s’affichent ensemble et ils sont empilés les uns sur les autres dans le tableau.

   ![](assets/qibuilder7.png)

## Limites connues

Si vous tentez de modifier directement le tableau, le fichier [!UICONTROL Quick Insights Builder] (l’outil de remplissage du blanc) ne sera plus synchronisé. Vous pouvez restaurer les paramètres de Quick Insight précédents en accédant à **[!UICONTROL Help > Tutorials]** la page ou effacer le tableau en cliquant **[!UICONTROL Resync Builder]** en haut à droite du panneau Statistiques rapides.

Sinon, la création directe entraînera le comportement du tableau en tant que tableau à structure libre traditionnel, sans les fonctionnalités utiles pour les nouveaux utilisateurs.

