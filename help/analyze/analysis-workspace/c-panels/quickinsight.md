---
description: Le créateur d’aperçus rapides est un outil destiné aux nouveaux utilisateurs de Workspace qui les guide dans la création de tableaux de données et de visualisations.
title: Générateur d’informations rapides
translation-type: tm+mt
source-git-commit: 7fbeac0488fbe9b3d10d7c1242f31250f1c7dc16

---


# Générateur d’informations rapides

>[!IMPORTANT]
>
>**[!UICONTROL Quick Insights]** est actuellement limitée dans les tests et n’est pas encore accessible à tous les clients Adobe Analytics.

[!UICONTROL Quick Insights] fournit des conseils aux non-analystes et aux nouveaux utilisateurs de [!UICONTROL Analysis Workspace] pour apprendre à répondre rapidement et facilement aux questions commerciales. C&#39;est aussi un outil idéal pour les utilisateurs expérimentés qui veulent répondre rapidement à une question simple sans avoir à construire eux-mêmes un tableau.

Lors de votre premier début d’utilisation de cette [!UICONTROL Analysis Workspace]méthode, vous pouvez vous demander quelles visualisations seraient les plus utiles, quelles dimensions et mesures pourraient faciliter les statistiques, où faire glisser et déposer des éléments, où créer un segment, etc.

Pour y remédier, et en fonction de l’utilisation des composants de données dans votre propre société, [!UICONTROL Analysis Workspace][!UICONTROL Quick Insights] utilisez un algorithme qui vous présentera les dimensions, mesures, segments et plages de dates les plus populaires que votre société utilise.

[!UICONTROL Quick Insights] vous aide

* Créez correctement un tableau de données et une visualisation correspondante dans [!UICONTROL Analysis Workspace].
* Apprenez la terminologie et le vocabulaire pour les composants de base et les éléments de [!UICONTROL Analysis Workspace]base.
* Réalisez des ventilations simples de dimensions, ajoutez plusieurs mesures ou comparez facilement des segments au sein d’un même [!UICONTROL Freeform table]groupe.
* Modifiez ou testez divers types de visualisation pour trouver rapidement et intuitivement l&#39;outil de recherche pour votre analyse.

## Terminologie clé de base

Voici quelques-uns des termes de base que vous devez connaître. Chaque tableau de données se compose de deux blocs fonctionnels (composants) ou plus que vous utilisez pour raconter l’historique de vos données.

| Bloc de création (composant) | Définition |
|---|---|
| [!UICONTROL Dimension] | Les dimensions sont des descriptions ou des caractéristiques des données de mesure qui peuvent être visualisées, ventilées et comparées dans un projet. Il s’agit de valeurs et de dates non numériques qui se divisent en éléments de dimension. Par exemple, &quot;navigateur&quot; ou &quot;page&quot; sont des dimensions. |
| [!UICONTROL Dimension item] | Les éléments de dimension sont des valeurs individuelles pour une dimension. Par exemple, les éléments de dimension pour la dimension de navigateur seraient &quot;Chrome&quot;, &quot;Firefox&quot;, &quot;Edge&quot;, etc. |
| [!UICONTROL Metric] | Les mesures sont des informations quantitatives sur l’activité des visiteurs, telles que les affichages, les clics publicitaires, les actualisations, la durée moyenne de consultation, les unités, les commandes, les recettes, etc. |
| [!UICONTROL Visualization] | Workspace offre [un certain nombre de visualisations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) pour créer des représentations visuelles de vos données, telles que des graphiques à barres, des graphiques en anneau, des histogrammes, des diagrammes en courbes, des cartes, des tracés différés, etc. |
| [!UICONTROL Breakdown] | Une ventilation permet de ventiler une dimension selon d’autres dimensions. Dans notre exemple, vous pouvez ventiler les États américains en fonction des périphériques mobiles pour obtenir les visites des périphériques mobiles par état, ou vous pouvez ventiler les périphériques mobiles en fonction des types de périphériques mobiles, des régions, des campagnes internes, etc. |
| [!UICONTROL Segment] | Les segments vous permettent d’identifier des sous-ensembles de visiteurs en fonction de caractéristiques ou d’interactions sur le site Web. Par exemple, vous pouvez créer [!UICONTROL Visitor] des segments basés sur des attributs : type de navigateur, périphérique, nombre de visites, pays, sexe ou selon les interactions : campagnes, recherche de mots-clés, moteur de recherche ou en fonction des sorties et des entrées : visiteurs de Facebook, d’un landing page défini, d’un domaine référent ou basés sur des variables personnalisées : champ de formulaire, catégories définies, ID de client. |

## Prise en main de Quick Insights

1. Connectez-vous à Adobe Analytics à l’aide des informations d’identification qui vous ont été fournies.
1. Accédez à [!UICONTROL Workspace] , cliquez sur **[!UICONTROL Create New Project]** , puis sur **[!UICONTROL Quick Insights]**.

   ![](assets/qibuilder.png)

1. Lorsque vous sortez du début, passez en revue le court didacticiel qui vous enseigne certaines des [!UICONTROL Quick Insights panel] bases. Ou cliquez sur pour **[!UICONTROL Skip Tutorial]**.
1. Sélectionnez vos blocs de création (également appelés composants) : dimensions (orange), mesures (vert), segments (bleu) ou plages de dates (violet) Vous devez sélectionner au moins une dimension et une mesure pour qu’un tableau soit automatiquement créé.

   ![](assets/qibuilder2.png)

   Vous pouvez sélectionner les blocs de création de trois manières différentes :
   * Faites-les glisser depuis le rail de gauche.
   * Si vous savez ce que vous cherchez : Tapez un Début et [!UICONTROL Quick Insights] remplissez les blancs pour vous.
   * Cliquez sur la liste déroulante et recherchez la liste.

1. Lorsque vous avez ajouté au moins une dimension et une mesure, les éléments suivants sont créés pour vous :

   * Tableau à structure libre avec la dimension (ici, Etats-Unis) verticalement et la mesure (ici, Visites) horizontalement en haut. Consultez ce tableau :
   ![](assets/qibuilder3.png)

   * Visualisation connexe, dans ce cas un graphique [à](/help/analyze/analysis-workspace/visualizations/bar.md)barres. La visualisation qui est générée dépend du type de données que vous avez ajoutées au tableau. Vous pouvez modifier le type de visualisation en cliquant sur la flèche de liste déroulante en regard de **[!UICONTROL Bar]**.


1. (Facultatif) Recherchez les dimensions et affichez les éléments de dimension en cliquant sur la flèche > à droite en regard de la dimension.

1. Essayez d&#39;ajouter d&#39;autres perfectionnements comme décrit ci-dessous sous &quot;Autres options utiles&quot;.

## Autres options utiles

D&#39;autres conseils utiles apparaîtront dans le [!UICONTROL Quick Insights Builder], certains selon votre dernière action.

* Commencez par suivre le **[!UICONTROL More tips]** didacticiel : Accédez-y via l’aide (?) en regard du [!UICONTROL Quick Insights Panel] titre.

   ![](assets/qibuilder4.png)

* **Ventilation par**: Vous pouvez utiliser jusqu’à 3 niveaux de ventilations sur les dimensions pour analyser en détail les données dont vous avez réellement besoin.

   ![](assets/qibuilder5.png)

* **Ajouter plus de mesures**: Vous pouvez ajouter jusqu’à 2 mesures supplémentaires en utilisant l’opérateur ET pour les ajouter au tableau.

   ![](assets/qibuilder6.png)

* **Ajouter d’autres segments**: Vous pouvez ajouter jusqu’à 2 segments supplémentaires en utilisant les opérateurs ET ou OU pour les ajouter au tableau. Regardez ce qui se passe dans le tableau lorsque vous ajoutez des utilisateurs mobiles OU des Visiteurs fidèles. Ils sont situés les uns à côté des autres, au-dessus des mesures. Si vous ajoutiez Utilisateurs mobiles ET Visiteurs fidèles, les résultats des deux segments s’afficheraient ensemble et ils seraient empilés les uns sur les autres dans le tableau.

   ![](assets/qibuilder7.png)

## Limites connues

Si vous tentez de modifier directement le tableau, le [!UICONTROL Quick Insights] panneau (l’outil de remplissage du blanc) ne sera plus synchronisé. Vous pouvez restaurer les paramètres précédents en cliquant [!UICONTROL Quick Insights] **[!UICONTROL Resync Builder]** en haut à droite du panneau.

![](assets/qibuilder9.png)

Vous recevrez un avertissement avant d’ajouter quelque chose directement au tableau :

![](assets/qibuilder8.png)

Dans le cas contraire, la création directe entraînera le comportement du tableau en tant que tableau à structure libre traditionnel, sans les fonctionnalités utiles pour les nouveaux utilisateurs.

