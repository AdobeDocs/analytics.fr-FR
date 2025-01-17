---
title: Panneau de comparaison des segments - Aperçu
description: Découvrez comment utiliser le panneau de comparaison des segments, un composant de Segment IQ dans Analysis Workspace.
keywords: Analysis Workspace ; Segment IQ
feature: Segmentation
role: User, Admin
exl-id: 1f5df6fb-1e9f-4b8f-885c-bf9e68d88c89
source-git-commit: 60836f5632cfd19d94f33441eaa9d949609d5712
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 92%

---

# Panneau de comparaison des segments - Aperçu {#segment-comparison-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_button"
>title="Comparaison des segments"
>abstract="Comparez rapidement deux segments sur tous les points de données afin de rechercher automatiquement les différences pertinentes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_panel"
>title="Panneau de comparaison des segments"
>abstract="Comparez rapidement deux segments sur tous les points de données afin de rechercher automatiquement les différences pertinentes.<br/><br/>**Paramètres **<br/>**Ajouter un segment** : premier segment à analyser.<br/>**Comparer avec** : deuxième segment par rapport auquel vous souhaitez effectuer une comparaison. Ce champ est automatiquement renseigné avec *Tout le monde* qui est l’inverse de votre premier segment. Si vous le souhaitez, vous pouvez le remplacer par un autre segment.<br/>**Paramètres avancés** : possibilité d’exclure des composants de l’analyse dans la comparaison des segments."
<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

*Cet article présente le panneau Comparaison des segments dans **Adobe Analytics**.<br/>Il n’existe pas de panneau équivalent dans **Customer Journey Analytics**.*

>[!ENDSHADEBOX]

Le panneau de comparaison des segments est un composant d’outil de [Segment IQ](../../segment-iq.md) qui détecte les différences les plus significatives sur le plan statistique parmi un nombre illimité de segments. La fonction effectue une itération au moyen d’une analyse automatisée de toutes les dimensions et mesures auxquelles vous avez accès. Les principales caractéristiques des segments d’audience qui stimulent les indicateurs clés de performances de votre entreprise sont ainsi détectées et vous pouvez savoir de cette façon à quel point des segments se chevauchent.

+++ Voici une vidéo sur la comparaison des segments :

>[!VIDEO](https://video.tv.adobe.com/v/23976/?quality=12)

+++

## Utilisation

Pour utiliser un panneau **[!UICONTROL Attribution]** :

1. Créez un panneau **[!UICONTROL Attribution]**. Pour plus d’informations sur la création d’un panneau, consultez [Créer un panneau](../panels.md#create-a-panel).

1. Spécifiez l’[entrée](#panel-input) du panneau.

1. Observez la [sortie](#panel-output) du panneau.



### Entrée du panneau

![Panneau Comparaison](assets/seg-compare-panel.png)

1. Sélectionnez les segments à comparer et faites-les glisser dans le panneau.

   ![Comparaison d’audiences](assets/compare-audiences.png)

   Après avoir fait glisser le segment dans le panneau, Analytics crée automatiquement un segment [!UICONTROL « Tous les autres »] qui comprend quiconque N’est PAS dans le segment que vous choisissez. Il s’agit d’un segment fréquemment utilisé dans le panneau de comparaison, mais vous avez la possibilité de le supprimer et de comparer un autre segment de votre choix.

   ![Tous les autres](assets/everyone-else.png)

1. Une fois que vous avez déterminé les deux segments à comparer, cliquez sur [!UICONTROL Créer].

   Cette action lance un processus principal qui recherche les différences statistiques entre les deux segments sélectionnés et l’ensemble des dimensions, des mesures et des autres segments. Une barre de progression en haut du panneau indique le temps restant jusqu’à ce que chaque mesure et dimension soit analysée. Les mesures, dimensions et segments les plus fréquemment utilisés s’exécutent en priorité. Dès lors, les résultats les plus pertinents sont renvoyés en temps voulu.

## Exclusion de composants de la comparaison

Il est parfois souhaitable d’exclure certaines dimensions, mesures ou segments des comparaisons de segments. Par exemple, vous souhaitez comparer le segment « Utilisateurs mobiles américains » à « Utilisateurs mobiles allemands ». L’inclusion de dimensions liées à la géographie n’aurait aucun sens, puisque ces segments impliquent déjà ces différences.

1. Une fois que les deux segments souhaités s’affichent dans le panneau, cliquez sur [!UICONTROL « Afficher les options avancées »].
1. Faites glisser les composants que vous souhaitez exclure dans le panneau [!UICONTROL Composants exclus].

   ![Composants exclus](assets/excluded-components.png)

Cliquez sur [!UICONTROL « Définir comme valeur par défaut »] pour exclure automatiquement vos composants actuels de toutes les futures comparaisons de segments. Si vous souhaitez modifier des composants exclus, cliquez sur un type de composant, puis sur le « X » en regard d’un composant afin de l’inclure à nouveau dans votre analyse. Cliquez sur « Effacer tout » pour inclure à nouveau tous les composants dans la comparaison de segments.

![Dimensions exclues](assets/excluded-dimensions.png)

### Sortie du panneau

Une fois l’analyse des deux segments souhaités terminée, Adobe affiche ses résultats au moyen de plusieurs visualisations :

![Visualisations 1](assets/new-viz.png)

![Visualisations 2](assets/new-viz2.png)

#### Taille et chevauchement

Illustre les tailles comparatives de chaque segment sélectionné et l’ampleur de leur chevauchement à l’aide d’un diagramme de Venn. Pointez sur le visuel pour savoir combien de visiteurs se trouvent dans chaque section en intersection ou non. Cliquez avec le bouton droit de la souris sur l’intersection afin de créer un nouveau segment pour une analyse plus approfondie. Si les deux segments s’excluent mutuellement, aucun chevauchement n’est affiché entre les deux cercles (généralement dans le cas de segments utilisant un conteneur d’accès).

![Taille et chevauchement](assets/size-overlap.png)

#### Résumés de population

Le nombre total de visiteurs uniques dans chaque segment et chevauchement s’affiche à droite de la visualisation Taille et chevauchement.

![Résumés de population](assets/population_summaries.png)

#### Mesures principales

Affiche les mesures les plus significatives sur le plan statistique entre les deux segments. Chaque ligne de ce tableau représente une mesure de différenciation, classée selon le degré de différence entre chaque segment. Un score de différence de 1 signifie qu’il est statistiquement significatif, tandis qu’un score de différence de 0 signifie qu’il n’y a aucune signification statistique.

Cette visualisation est similaire aux tableaux à structure libre dans Analysis Workspace. Si vous souhaitez approfondir l’analyse d’une mesure spécifique, passez la souris sur un élément de ligne et cliquez sur « Créer un visuel ». Un tableau est alors créé pour analyser cette mesure spécifique. Si une mesure n’est pas pertinente pour votre analyse, passez la souris sur l’élément de ligne et cliquez sur le « X » pour le supprimer.

>[!NOTE]
>
>Les mesures ajoutées à ce tableau au terme de la comparaison de segments ne reçoivent pas de score de différence.

![Mesures principales](assets/top-metrics.png)

#### Mesure dans le temps par segment

Une visualisation liée se trouve à droite du tableau de mesures. Vous pouvez cliquer sur un élément de ligne du tableau de gauche afin que cette visualisation se mette à jour pour afficher les tendances de cette mesure au fil du temps.

![Ligne Mesures principales](assets/linked-viz.png)

#### Dimensions principales

Affiche les éléments de dimension les plus significatifs sur le plan statistique pour toutes vos dimensions. Chaque ligne présente le pourcentage de chaque segment exposant cet élément de dimension. Par exemple, ce tableau peut indiquer que 100 % des visiteurs du « segment A » avaient l’élément de dimension « Type de navigateur : Google », tandis que 19,6 % du « segment B » seulement ont cet élément de dimension. Un score de différence de 1 signifie qu’il est statistiquement significatif, tandis qu’un score de différence de 0 signifie qu’il n’y a aucune signification statistique.

Cette visualisation est similaire aux tableaux à structure libre dans Analysis Workspace. Si vous souhaitez approfondir l’analyse d’un élément de dimension spécifique, passez la souris sur un élément de ligne et cliquez sur « Créer un visuel ». Un tableau est alors créé pour analyser cet élément de dimension spécifique. Si un élément de dimension n’est pas pertinent pour votre analyse, passez la souris sur l’élément de ligne et cliquez sur le « X » pour le supprimer.

>[!NOTE]
>
>Les éléments de dimension ajoutés à ce tableau au terme de la comparaison de segments ne reçoivent pas de score de différence.

![Dimensions principales](assets/top-dimension-item1.png)

#### Éléments de dimension par segment

Une visualisation de graphique à barres liée se trouve à droite du tableau de dimensions. Elle affiche tous les éléments de dimension affichés dans un graphique à barres. Cliquez sur un élément de ligne dans le tableau de gauche pour mettre à jour la visualisation sur la droite.

![Graphique à barres des dimensions principales](assets/top-dimension-item.png)

#### Segments principaux

Indique quels autres segments (différents des deux segments sélectionnés pour la comparaison) présentent un chevauchement statistiquement significatif. Par exemple, ce tableau peut présenter un troisième segment, « Visiteurs récurrents », qui chevauche nettement le « segment A », mais pas le « segment B ». Un score de différence de 1 signifie qu’il est statistiquement significatif, tandis qu’un score de différence de 0 signifie qu’il n’y a aucune signification statistique.

Cette visualisation est similaire aux tableaux à structure libre dans Analysis Workspace. Si vous souhaitez approfondir l’analyse d’un segment spécifique, passez la souris sur un élément de ligne et cliquez sur « Créer un visuel ». Un tableau est alors créé pour analyser ce segment spécifique. Si un segment n’est pas pertinent pour votre analyse, passez la souris sur l’élément de ligne et cliquez sur le « X » pour le supprimer.

>[!NOTE]
>
>Les segments ajoutés à ce tableau au terme de la comparaison de segments ne reçoivent pas de score de différence.

![Segments principaux](assets/top-segments.png)

#### Chevauchement des segments

Une visualisation Diagramme de Venn liée se trouve à droite du tableau de segments. Il montre le segment le plus significatif sur le plan statistique appliqué à vos segments comparés. Par exemple, « Segment A » + « Segment significatif sur le plan statistique » ou « Segment B » + « Segment significatif sur le plan statistique ». Cliquez sur un élément de ligne dans le tableau de gauche pour mettre à jour le diagramme de Venn sur la droite.

![Diagramme de Venn Segments principaux](assets/segment-overlap.png)
