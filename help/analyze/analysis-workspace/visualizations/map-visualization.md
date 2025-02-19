---
description: Utilisation de la visualisation par cartes dans un projet Workspace.
title: Carte
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
source-git-commit: e0d14f6dd7be438f3dad979abcfc279e710873e7
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 62%

---

# Carte {#map}

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="Carte"
>abstract="Cette visualisation représente les mesures en les superposant sur une carte. Cette visualisation s’avère utile pour identifier les données dans différentes zones géographiques."

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

_Cet article présente la visualisation des cartes dans_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Actuellement, aucune visualisation de carte n’est disponible dans_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._

>[!ENDSHADEBOX]



La visualisation ![Globe](/help/assets/icons/Globe.svg) **[!UICONTROL Map]** dans Analysis Workspace

* vous permet de créer une carte visuelle de n’importe quelle mesure (y compris les mesures calculées),
* est utile pour identifier et comparer des données de mesures dans différentes régions géographiques,
* peut prendre en charge 2 sources de données : latitude/longitude à partir de l’utilisation mobile ou dimension géographique pour l’utilisation du web,
* prend en charge l’exportation de PDF ; et
* utilise WebGL pour l&#39;affichage des graphiques. Si vos pilotes graphiques ne prennent pas en charge le rendu WebGL, il se peut que vous deviez les mettre à jour.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualisation des cartes dans Analysis Workspace](https://video.tv.adobe.com/v/23559/?quality=12){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Utilisation

1. Ajoutez une visualisation ![Carte](/help/assets/icons/Globe.svg) [!UICONTROL Carte]. Voir [Ajouter une visualisation à un panneau](freeform-analysis-visualizations.md#add-visualizations-to-a-panel). Vous pouvez uniquement faire glisser une visualisation Carte au-dessus d’un tableau à structure libre.

   ![Configuration du mappage](assets/map-configuration.png){width="50%"}

1. Dans les listes déroulantes, sélectionnez une mesure. Vous pouvez également faire glisser une mesure depuis la liste des mesures (y compris les mesures calculées).
1. Spécifiez la source de données à partir de laquelle vous souhaitez dessiner. Cette boîte de dialogue s’affiche uniquement si le suivi de l’emplacement est activé pour les données des applications mobiles.

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
      * Avec des mesures de type *pourcentage*, la mise en grappe établit la moyenne des pourcentages.
      * Un jeu de couleurs vert/rouge : positif/négatif.

   * **Faire pivoter** la carte en 2D ou en 3D en maintenant la touche [!UICONTROL Ctrl] et en déplaçant la carte.

   * **Basculer** vers une autre vue, comme une carte thermique, en utilisant les [paramètres](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E) décrits ci-dessous. La vue à bulles est la vue par défaut.

1. **Enregistrer** le projet pour enregistrer tous les paramètres des cartes (coordonnées, zoom, rotation).
1. Le tableau à structure libre, sous la visualisation, peut être renseigné en faisant glisser les dimensions et mesures d’emplacement depuis le rail de gauche.



## Configurer

Pour reconfigurer la visualisation des cartes, sélectionnez ![Modifier](/help/assets/icons/Edit.svg).


## Paramètres

Pour définir les paramètres de la visualisation, sélectionnez ![Paramètre](/help/assets/icons/Setting.svg).

| Paramètre | Description |
|--- |--- |
| **[!UICONTROL Type de carte]** | |
| [!UICONTROL Bulles] | Représente les événements à l’aide de bulles. Un graphique en bulles est un graphique à plusieurs variables à mi-chemin entre un graphique de dispersion et un graphique à zones proportionnelles. Il s’agit de la vue par défaut. |
| Carte thermique | Représente les événements à l’aide d’une carte thermique. Une carte thermique est une représentation graphique des données où les valeurs individuelles contenues dans une matrice sont représentées sous la forme de couleurs. |
| **[!UICONTROL Styles]** | |
| [!UICONTROL Thème de couleur] | Affiche le jeu de couleurs pour la carte thermique et les bulles. Vous avez le choix entre Corail, Rouges, Verts ou Bleus. La valeur par défaut est Coral. |
| [!UICONTROL Style de carte] | Vous pouvez choisir entre Basic, Streets, Bright, Light, Dark et Satellite. |
| **[!UICONTROL Rayon du cluster]** | Regroupe les points de données qui se trouvent dans le nombre spécifié de pixels. La valeur par défaut est de 50. |
| **[!UICONTROL Valeur Max Personnalisée]** | Permet de modifier le seuil de la valeur maximale pour la carte. Le fait de modifier cette valeur ajuste l’échelle des valeurs de bulles/de la carte thermique (couleur et taille) en fonction de la valeur maximale personnalisée définie. |

<!--
## Build a time-parting heatmap

Here is a video on the topic:

>[!VIDEO](https://video.tv.adobe.com/v/26991/?quality=12)

-->

