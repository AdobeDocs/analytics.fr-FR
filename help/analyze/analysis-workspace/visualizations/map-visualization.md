---
description: Utiliser la visualisation des cartes pour tracer des données sur une visualisation de carte géographique
title: Carte
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
source-git-commit: 978bd8642011dd2c8e43564c90303f194689a64e
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 97%

---

# Carte {#map}

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="Carte"
>abstract="Cette visualisation représente les mesures en les superposant sur une carte. Cette visualisation est utile pour identifier les données dans différentes régions géographiques."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_bubbles"
>title="Bulles"
>abstract="Représente les événements à l’aide de bulles."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_heatmap"
>title="Carte thermique"
>abstract="Tracer des événements à l’aide d’une carte thermique."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Cet article présente la visualisation Carte dans_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Actuellement, aucune visualisation Carte n’est disponible dans_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._

>[!ENDSHADEBOX]



La visualisation ![Globe](/help/assets/icons/Globe.svg) **[!UICONTROL Carte]** dans Analysis Workspace

* permet de créer une carte visuelle de n’importe quelle mesure (y compris les mesures calculées) ;
* est pratique pour identifier et comparer les données de mesure de différentes régions géographiques ;
* peut prendre en charge 2 sources de données : la latitude et la longitude à partir de l’utilisation mobile ou la dimension géographique à partir de l’utilisation du web ;
* prend en charge l’export au format PDF ;
* tire parti de WebGL pour l’affichage des graphiques. Si vos pilotes graphiques ne prennent pas en charge le rendu WebGL, il se peut que vous deviez les mettre à jour.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualisation Carte dans Analysis Workspace](https://video.tv.adobe.com/v/41503/?quality=12&captions=fre_fr){target=&#34;_blank&#34;} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Utilisation

1. Ajoutez une visualisation ![Carte](/help/assets/icons/Globe.svg) [!UICONTROL Carte]. Voir [Ajouter une visualisation à un panneau](freeform-analysis-visualizations.md#add-visualizations-to-a-panel). Vous pouvez uniquement faire glisser une visualisation Carte au-dessus d’un tableau à structure libre.

   ![Configuration de la carte](assets/map-configuration.png){width="50%"}

1. Dans les listes déroulantes, sélectionnez une mesure. Faites glisser une mesure depuis la liste des mesures (mesures calculées comprises).
1. Spécifiez la source de données à partir de laquelle le tracé doit être effectué. Cette boîte de dialogue apparaît uniquement si le suivi de l’emplacement est activé pour les données des applications mobiles.

   | Source | Description |
   | --- | --- |
   | **[!UICONTROL Lat/Long pour applications mobiles]** | Cette option représente les données des applications mobiles. Cette option apparaît uniquement si vous l’avez activée pour votre suite de rapports sous [!UICONTROL Analytics] > [!UICONTROL Administration] > [!UICONTROL Suites de rapports] > (sélectionnez la suite de rapports) > [!UICONTROL Modifier les paramètres] > [!UICONTROL Gestion mobile] > [!UICONTROL Activer le suivi de l’emplacement]. Ces paramètres sont ceux par défaut (si le suivi de l’emplacement est activé). |
   | **[!UICONTROL Dimension géographique]** | Cette option représente les données de segmentation géographique relatives à l’emplacement du visiteur sur la base de son adresse IP. Ces données sont transformées en [!UICONTROL pays], [!UICONTROL région] et [!UICONTROL ville]. Notez toutefois qu’elles ne vont pas jusqu’au niveau de la DMA ou du code postal. Cette dimension est activée pour pratiquement toutes les suites de rapports. Si ce n’est pas le cas pour la vôtre, contactez l’assistance clientèle Adobe pour faire activer les rapports géographiques. |

1. Sélectionnez la **[!UICONTROL Version]**.

   Une visualisation de carte du monde avec des bulles est générée.

   ![](assets/bubble-world-view.png)

1. Vous pouvez maintenant :

   * **Zoomer** sur cette carte pour agrandir certaines zones en double-cliquant sur la carte ou en utilisant la molette de défilement. La carte s’agrandit en fonction de l’endroit où se trouve le curseur. Lors de l’agrandissement, la dimension requise (pays > état > ville) est automatiquement mise à jour en fonction du niveau de zoom.
   * **Comparer** deux visualisations de cartes ou plus dans le même projet en les plaçant côte à côte.
   * **Afficher les comparaisons d’une période à l’autre (par exemple, d’une année à l’autre)** :

      * Afficher des nombres négatifs : par exemple, si vous tracez une mesure d’une année à l’autre, la carte peut afficher -33 % sur New York.
      * Avec les mesures de type *pourcentage*, le regroupement effectue la moyenne des pourcentages.
      * Un jeu de couleurs vert/rouge : positif/négatif.

   * **Faire pivoter** la carte en 2D ou en 3D en maintenant la touche [!UICONTROL Ctrl] et en déplaçant la carte.

   * **Basculer** vers une autre vue, comme une carte thermique, en utilisant les [paramètres](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E) décrits ci-dessous. La vue à bulles est la vue par défaut.

1. **Enregistrer** le projet pour enregistrer tous les paramètres des cartes (coordonnées, zoom, rotation).
1. Le tableau à structure libre, sous la visualisation, peut être rempli en faisant glisser des dimensions et des mesures depuis le rail de gauche.



## Configurer

Pour reconfigurer la visualisation Carte, sélectionnez ![Modifier](/help/assets/icons/Edit.svg).


## Paramètres

Pour définir les paramètres de la visualisation, sélectionnez ![Paramètre](/help/assets/icons/Setting.svg).

| Paramètre | Description |
|--- |--- |
| **[!UICONTROL Type de carte]** | |
| **[!UICONTROL Bulles] | Représente les événements à l’aide de bulles. Un graphique en bulles est un graphique à plusieurs variables à mi-chemin entre un graphique de dispersion et un graphique à zones proportionnelles. Il s’agit de l’affichage par défaut. |
| [!UICONTROL &#x200B; Carte thermique &#x200B;] | Représente les événements à l’aide d’une carte thermique. Une carte thermique est une représentation graphique des données où les valeurs individuelles contenues dans une matrice sont représentées sous la forme de couleurs. |
| **[!UICONTROL Styles]** | |
| [!UICONTROL Thème de couleur] | Affiche le jeu de couleurs pour la carte thermique et les bulles. Vous avez le choix entre Corail, Rouges, Verts ou Bleus. La valeur par défaut est Corail. |
| [!UICONTROL Style de carte] | Vous avez le choix entre De base, Rues, Lumineux, Clair, Foncé et Satellite. |
| **[!UICONTROL Rayon du groupe]** | Regroupe les points de données qui se trouvent dans le nombre spécifié de pixels. La valeur par défaut est de 50. |
| **[!UICONTROL Valeur max. personnalisée]** | Permet de modifier le seuil de la valeur maximale pour la carte. Le fait de modifier cette valeur ajuste l’échelle des valeurs de bulles/de la carte thermique (couleur et taille) en fonction de la valeur maximale personnalisée définie. |

<!--
## Build a time-parting heatmap

Here is a video on the topic:

>[!VIDEO](https://video.tv.adobe.com/v/35002/?quality=12&captions=fre_fr)

-->

