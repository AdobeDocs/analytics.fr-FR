---
description: Dans Analysis Workspace, vous pouvez créer des segments d’après un point de contact, ajouter des segments comme point de contact et comparer des processus clés pour plusieurs segments.
keywords: abandons et segmentation ; segments dans l'analyse des abandons ; comparaison des segments dans les abandons
seo-description: Dans Analysis Workspace, vous pouvez créer des segments d’après un point de contact, ajouter des segments comme point de contact et comparer des processus clés pour plusieurs segments.
seo-title: Application de segments dans l'analyse des abandons
title: Application de segments dans l'analyse des abandons
uuid: e 87 a 33 df -160 e -4943-8 d 02-4 d 6609 ae 3 bb 1
translation-type: tm+mt
source-git-commit: 769d076549484c6939157ef217225493ddbe130e

---


# Application de segments dans l'analyse des abandons

Dans Analysis Workspace, vous pouvez créer des segments d’après un point de contact, ajouter des segments comme point de contact et comparer des processus clés pour plusieurs segments.

>[!IMPORTANT]
>Les segments utilisés comme points de contrôle dans les abandons doivent utiliser un conteneur à un niveau inférieur à celui de la visualisation Abandons. Avec un abandon de contexte de visiteur, les segments utilisés comme checkpoints de contrôle doivent être des segments de visite ou d'accès. Avec un abandon contexte de visite, les segments utilisés comme checkpoint de contrôle doivent être des segments basés sur les accès. Si vous utilisez une combinaison non valide, l'abandon est de 100 %. Nous avons ajouté un avertissement à la visualisation Abandons qui s'affichera lorsque vous ajouterez un segment incompatible comme touchpoint de contact. Certaines combinaisons de conteneur de segments non valides conduisent à des diagrammes d'abandons non valides, tels que

>* l’utilisation d’un segment basé sur les visiteurs comme point de contact dans une visualisation Abandons sur base du visiteur
>* l’utilisation d’un segment basé sur les visiteurs comme point de contact dans une visualisation Abandons sur base de la visite
>* l’utilisation d’un segment basé sur les visites comme point de contact dans une visualisation Abandons sur base de la visite


## Create a segment from a touchpoint {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Commencez par créer un segment d’après un point de contact donné qui vous intéresse particulièrement et qu’il peut être utile d’appliquer à d’autres rapports. Pour ce faire, cliquez avec le bouton droit de la souris sur un point de contact, puis sélectionnez **[!UICONTROL Créer un segment d’après le point de contact]**.

   ![](assets/segment-from-touchpoint.png)

   Le créateur de segments s’ouvre ; il est prérenseigné avec le segment séquentiel prédéfini qui correspond au point de contact que vous avez sélectionné :

   ![](assets/segment-builder.png)

1. Nommez et décrivez le segment, puis enregistrez-le.

   Vous pouvez maintenant utiliser ce segment où vous le souhaitez.

## Add a segment as a touchpoint {#section_17611C1A07444BE891DC21EE8FC03EFC}

Si, par exemple, pour vos utilisateurs aux États-Unis, vous souhaitez connaître les tendances qui se dégagent et de quelle façon les abandons sont affectés, faites glisser le segment correspondant à ces utilisateurs sur l’abandon :

![](assets/segment-touchpoint.png)

Vous pouvez aussi créer un point de contact ET en faisant glisser le segment des utilisateurs aux États-Unis sur un autre point de contrôle.

## Compare segments in fallout {#section_E0B761A69B1545908B52E05379277B56}

Vous pouvez comparer un nombre illimité de segments dans la visualisation Abandons.

1. Sélectionnez les segments que vous souhaitez comparer dans le rail [!UICONTROL Segments] de gauche. Dans notre exemple, nous avons sélectionné deux segments : Utilisateurs aux États-Unis et Utilisateurs hors des États-Unis.
1. Faites-les glisser dans la zone de dépôt Segment en haut de l’écran.

   ![](assets/segment-drop.png)

1. Facultatif : vous pouvez conserver le conteneur par défaut Toutes les visites ou le supprimer.

   ![](assets/seg-compare.png)

1. Vous pouvez maintenant comparer les abandons des deux segments, par exemple pour savoir quand un segment est plus performant qu’un autre, entre autres.

