---
title: Présentation du panneau de comparaison de segments
description: Découvrez comment utiliser le panneau de comparaison de segments, composant de la QI de segment dans Analysis Workspace.
keywords: Espace de travail d’analyse;QI du segment
solution: Analytics
translation-type: tm+mt
source-git-commit: ca9f1ed00295b556250894ae4e7fa377ef8a593d

---


# Présentation du panneau de comparaison de segments

Le panneau de comparaison de segments est un composant d’outil de la QI [du](../../segment-iq.md) segment qui détecte les différences les plus significatives sur le plan statistique entre un nombre illimité de segments. La fonction effectue une itération au moyen d’une analyse automatisée de toutes les dimensions et mesures auxquelles vous avez accès. Il détecte automatiquement les caractéristiques clés des segments d’audience qui génèrent les indicateurs clés de performance de votre entreprise et vous permet de voir combien de segments se chevauchent.

## Création d’un panneau de comparaison de segments

1. Connectez-vous à [experience.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe.
1. Cliquez sur l’icône de 9 carrés dans l’angle supérieur droit, puis sur le logo Analytics coloré.
1. Dans la barre de navigation supérieure, cliquez sur Espace de travail.
1. Cliquez sur le bouton Créer un projet.
1. Dans la fenêtre contextuelle modale, assurez-vous que l’option "Projet vierge" est sélectionnée, puis cliquez sur Créer.
1. Cliquez sur le bouton Panneaux sur la gauche, puis faites glisser le panneau Comparaison des segments au-dessus ou au-dessous du panneau du tableau à structure libre créé automatiquement.

   ![Panneau Comparaison](assets/seg-compare-panel.png)

1. Sélectionnez les segments à comparer et faites-les glisser dans le panneau.

   ![Comparaison des audiences](assets/compare-audiences.png)

   Une fois que vous avez fait glisser un segment dans le panneau, Analytics crée automatiquement un [!UICONTROL ’segment Tous les autres] qui inclut les personnes NE figurant PAS dans le segment choisi. Il s’agit d’un segment fréquemment utilisé dans le panneau de comparaison, mais vous êtes libre de le supprimer et de comparer un autre segment de choix.

   ![Tous les autres](assets/everyone-else.png)

1. Une fois que vous avez déterminé les deux segments à comparer, cliquez sur [!UICONTROL Créer].

   Cette action lance un processus principal qui recherche les différences statistiques entre les deux segments sélectionnés et toutes les dimensions, mesures et autres segments. Une barre de progression en haut du panneau indique le temps restant jusqu’à ce que chaque mesure et dimension soit analysée. Les mesures, dimensions et segments les plus fréquemment utilisés sont prioritaires pour s’exécuter en premier afin que les résultats les plus pertinents soient renvoyés en temps voulu.

## Exclure les composants de la comparaison

Il est parfois souhaitable d’exclure certaines dimensions, mesures ou segments des comparaisons de segments. Par exemple, vous souhaitez comparer le segment Utilisateurs mobiles américains à Utilisateurs mobiles allemands. L’inclusion de dimensions liées à la géographie n’aurait aucun sens puisque ces segments impliquent déjà ces différences.

1. Une fois les deux segments souhaités présents dans le panneau, cliquez sur [!UICONTROL 'Afficher les options avancées'].
1. Drag and drop components you want to exclude into the [!UICONTROL Excluded Components] panel.

   ![Composants exclus](assets/excluded-components.png)

Cliquez sur [!UICONTROL "Définir comme valeur par défaut"] pour exclure automatiquement vos composants actuels dans toutes les futures comparaisons de segments. Si vous souhaitez modifier des composants exclus, cliquez sur un type de composant, puis cliquez sur le X en regard d’un composant pour le réinclure dans votre analyse. Cliquez sur Effacer tout pour réinclure tous les composants dans la comparaison de segments.

![Dimensions exclues](assets/excluded-dimensions.png)

## Affichage d’un rapport de comparaison de segments

Une fois l’analyse des deux segments souhaités terminée, Adobe affiche ses résultats au moyen de plusieurs visualisations :

![Visualisations 1](assets/new-viz.png)

![Visualisations 2](assets/new-viz2.png)

### Taille et chevauchement

Illustre les tailles comparatives de chaque segment sélectionné et leur chevauchement à l’aide d’un diagramme de Venn. Pointez sur le visuel pour savoir combien de visiteurs se trouvent dans chaque section en intersection ou non. Cliquez avec le bouton droit de la souris sur l’intersection afin de créer un nouveau segment pour une analyse plus approfondie. Si les deux segments s’excluent mutuellement, aucun chevauchement n’est affiché entre les deux cercles (généralement avec des segments utilisant un conteneur d’accès).

![Taille et chevauchement](assets/size-overlap.png)

### Résumés démographiques

À droite de la visualisation Taille et chevauchement, le nombre total de visiteurs uniques dans chaque segment et chevauchement s’affiche.

![Résumés démographiques](assets/population_summaries.png)

### Principales mesures

Affiche les mesures les plus significatives sur le plan statistique entre les deux segments. Chaque ligne de ce tableau représente une mesure de différenciation, classée selon le degré de différence entre chaque segment. Un score de différence de 1 signifie qu’il est statistiquement significatif, tandis qu’un score de différence de 0 signifie qu’il n’y a aucune signification statistique.

Cette visualisation est similaire aux tableaux à structure libre dans Analysis Workspace. Si vous souhaitez approfondir l’analyse d’une mesure spécifique, passez la souris sur une ligne et cliquez sur "Créer un visuel". Un nouveau tableau est créé pour analyser cette mesure spécifique. Si une mesure n’est pas pertinente pour votre analyse, passez la souris sur l’élément de ligne et cliquez sur le X pour le supprimer.

> [!NOTE] Les mesures ajoutées à ce tableau une fois la comparaison de segments terminée ne reçoivent pas de note de différence.

![Principales mesures](assets/top-metrics.png)

### Mesure dans le temps par segment

Une visualisation liée se trouve à droite du tableau de mesures. Vous pouvez cliquer sur une ligne du tableau de gauche et cette visualisation se met à jour pour afficher les tendances de cette mesure au fil du temps.

![Ligne des principales mesures](assets/linked-viz.png)

### Principales dimensions

Affiche les valeurs de dimension les plus significatives sur le plan statistique dans toutes vos dimensions. Chaque ligne affiche le pourcentage de chaque segment présentant cette valeur de dimension. Par exemple, ce tableau peut indiquer que 100 % des visiteurs du segment A possédaient l’élément de dimension "Type de navigateur : Google", alors que seulement 19,6 % du segment B possédaient cet élément de dimension. Un score de différence de 1 signifie qu’il est statistiquement significatif, tandis qu’un score de différence de 0 signifie qu’il n’y a aucune signification statistique.

Cette visualisation est similaire aux tableaux à structure libre dans Analysis Workspace. Si une analyse plus approfondie d’une valeur de dimension spécifique est souhaitée, passez la souris sur une ligne et cliquez sur "Créer un visuel". Un nouveau tableau est créé pour analyser cette valeur de dimension spécifique. Si une valeur de dimension n’est pas pertinente pour votre analyse, passez la souris sur l’élément de ligne et cliquez sur le X pour le supprimer.

> [!NOTE] Les valeurs de dimension ajoutées à ce tableau une fois la comparaison de segments terminée ne reçoivent pas de note de différence.

![Principales dimensions](assets/top-dimension-item1.png)

### Eléments de dimension par segment

À droite du tableau des dimensions se trouve une visualisation en graphique à barres liées. Il affiche toutes les valeurs de dimension affichées dans un graphique à barres. Le fait de cliquer sur une ligne dans le tableau de gauche met à jour la visualisation sur la droite.

![Graphique à barres des principales dimensions](assets/top-dimension-item.png)

### Principaux segments

Indique quels autres segments (autres que les deux segments sélectionnés pour la comparaison) présentent un chevauchement statistiquement significatif. Par exemple, ce tableau peut montrer qu’un troisième segment, "Visiteurs récurrents", chevauche fortement le segment A, mais ne chevauche pas le segment B. Un score de différence de 1 signifie qu’il est statistiquement significatif, tandis qu’un score de différence de 0 signifie qu’il n’y a aucune signification statistique.

Cette visualisation est similaire aux tableaux à structure libre dans Analysis Workspace. Si vous souhaitez effectuer une analyse plus approfondie sur un segment spécifique, passez la souris sur une ligne et cliquez sur "Créer un visuel". Un nouveau tableau est créé pour analyser ce segment spécifique. Si un segment n’est pas pertinent pour votre analyse, passez la souris sur l’élément de ligne et cliquez sur le X pour le supprimer.

> [!NOTE] Les segments ajoutés à ce tableau une fois la comparaison de segments terminée ne reçoivent pas de note de différence.

![Principaux segments](assets/top-segments.png)

### Chevauchement de segment

À droite du tableau des segments se trouve une visualisation de diagramme de Venn liée. Il montre le segment le plus significatif statistiquement appliqué à vos segments comparés. Par exemple, "Segment A" + "Segment statistiquement significatif" ou 'Segment B' + 'Segment statistiquement significatif'. Le fait de cliquer sur une ligne de segment dans le tableau de gauche met à jour le diagramme de Venn sur la droite.

![Diagramme VN des segments principaux](assets/segment-overlap.png)
