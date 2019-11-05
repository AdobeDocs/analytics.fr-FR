---
title: Création d’un rapport de base dans Analysis Workspace
description: Découvrez comment créer un rapport de base dans Analysis Workspace dans un format adapté aux utilisateurs familiarisés avec des outils tiers tels que Google Analytics.
translation-type: tm+mt
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Création d’un rapport de base dans Analysis Workspace pour les utilisateurs de Google Analytics

Analysis Workspace (l’une des principales fonctionnalités d’Adobe Analytics) fournit une zone fiable dans laquelle un utilisateur peut obtenir des informations sur les données collectées. La création de rapports est très différente entre Google Analytics et Adobe Analytics :

* La structure des rapports dans Google Analytics vous permet de sélectionner un type particulier de données, tel que l’emplacement géographique ou le trafic de référence. La plate-forme utilise une vue de création de rapports préfabriquée en fonction de la meilleure manière prévue d’afficher ces données.
* La structure des rapports d’Analysis Workspace offre un canevas vierge, offrant ainsi plus de souplesse pour répondre aux besoins de création de rapports exacts.

Comme Analysis Workspace fonctionne plus comme un canevas que des rapports préfabriqués, la recréation de rapports à partir de Google Analytics consiste simplement à utiliser les visualisations et les composants appropriés.

## Termes clés utilisés dans Workspace

* **Les panneaux** constituent les blocs de construction principaux de l’espace de travail. Dans presque tous les scénarios, un panneau à structure libre est utilisé.
* **Les visualisations** constituent tous les panneaux à structure libre. Leur but est de représenter les données sous différents formats. La plupart du temps ce format est un tableau, mais d'autres fois il peut être des choses comme un beignet ou un graphique en courbes. De nombreux rapports dans Google Analytics sont constitués de l’équivalent de deux visualisations : un graphique en courbes et un tableau à structure libre.
* **Les composants** sont placés dans une visualisation pour renvoyer des données. Les composants peuvent être mélangés de différentes manières pour répondre aux besoins de création de rapports.
   * **Les dimensions** sont des valeurs de variable et contiennent généralement du texte. Par exemple, nom de page, référent ou pays géographique. Ils sont généralement répertoriés sous forme de lignes dans un tableau.
   * **Les mesures** désignent généralement un événement ou une conversion d’une sorte ou d’une autre. Par exemple, des événements courants tels qu’une page vue ou quelque chose de plus important comme un achat ou un enregistrement. Elles sont généralement considérées comme des colonnes dans les tableaux pour indiquer le nombre de fois où cet événement s’est produit par dimension.
   * **Les segments** sont un sous-ensemble de vos données et se comportent de la même manière que les segments dans Google Analytics. Ils vous permettent de créer des filtres personnalisés, ce qui vous permet de vous concentrer sur une partie spécifique de vos données.
   * **Les plages** de dates vous permettent d’organiser les données selon le moment où un événement s’est produit. Elles constituent la colonne vertébrale de l’affichage des tendances au fil du temps et sont généralement associées à une mesure.

## Création d’un rapport de base dans Workspace

Créez un rapport Toutes les pages (similaire à celui de Google Analytics) en faisant glisser les composants appropriés sur un canevas d’espace de travail.

1. Connectez-vous à [experience.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur l’icône à 9 carrés dans l’angle supérieur droit, puis sur le logo Analytics coloré.
3. Dans la barre de navigation supérieure, cliquez sur Espace de travail.
4. Cliquez sur le bouton Créer un projet.
5. Dans la fenêtre contextuelle modale, assurez-vous que l’option "Projet vierge" est sélectionnée, puis cliquez sur Créer.
6. Sur la gauche, une liste de dimensions, de mesures, de segments et de plages de dates s’affiche. Localisez la dimension Pages (orange de couleur), puis faites-la glisser sur le canevas intitulé Déposer une dimension ici.
7. Un rapport présentant les principales pages de ce mois est visible. Analysis Workspace renseigne automatiquement le rapport avec la mesure [Occurrences](/help/components/c-variables/c-metrics/metrics-occurrences.md) .
8. Un tableau de Google Analytics contient généralement 7 à 8 mesures. Recherchez la mesure Taux de rebonds (vert couleur), puis faites-la glisser en regard de l’en-tête de mesure Occurrences. Si vous faites glisser la mesure Taux de rebonds en regard d’Occurrences, les deux mesures s’affichent côte à côte.
9. De nombreuses mesures peuvent être placées côte à côte en faisant glisser les mesures en regard des en-têtes de mesure existants. Pour plus d’informations sur la manière d’obtenir des mesures généralement utilisées dans Google Analytics, reportez-vous à la section Mesures [](common-metrics.md) fréquemment utilisées.

   ![Nouvelle mesure](/help/technotes/ga-to-aa//assets/new_metric.png)

## Commencer avec un modèle de rapport préconstruit dans Workspace

Créez le modèle Consommation de contenu (similaire au rapport Toutes les pages dans Google Analytics) en accédant à un modèle de projet.

1. Cliquez sur le bouton Créer un projet.
2. Recherchez et cliquez deux fois sur l’icône Consommation de contenu (Web) répertoriée sous Tous les modèles.
3. Parcourez chacune des visualisations prédéfinies : Flux de page d’entrée, Tableau des pages principales, Flux de page de sortie, Flux de section du site d’entrée et Tableau des sections du site supérieur.

   ![Sélection de modèle](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## Testez l'outil

Analysis Workspace étant un outil de création de rapports, il n’a aucun impact sur la collecte de données. Il n'y a aucune répercussion à faire glisser sans distinction des composants dans un projet pour voir ce qui fonctionne. Faites glisser différentes combinaisons de dimensions et de mesures dans votre projet d’espace de travail pour voir ce qui vous est disponible.

Si vous faites glisser accidentellement un composant non valide vers votre projet d’espace de travail ou souhaitez revenir en arrière d’une étape, appuyez sur ctrl+Z (Windows) ou cmd+Z (Mac) pour annuler la dernière action effectuée. Vous pouvez également commencer par une ardoise propre en cliquant sur *[!UICONTROL Projet]&gt;[!UICONTROL Nouveau]* dans le menu supérieur gauche.

Adobe a placé de nombreuses fonctionnalités dans Analysis Workspace dans le menu contextuel du clic droit. Il est possible de cliquer avec le bouton droit de la souris sur la plupart des visualisations et des composants pour une analyse et une interaction plus détaillées. Pensez à cliquer avec le bouton droit sur les composants de votre espace de travail pour voir quelles options sont disponibles.

## Comprendre les dimensions et les mesures à utiliser

Si vous êtes à l’aise avec Analysis Workspace et souhaitez recréer un rapport spécifique généralement affiché dans Google Analytics, recherchez le rapport sur sa page respective :

* [Rapports en temps réel](realtime-reports.md)
* [Rapports Audience](audience-reports.md)
* [Rapports d’acquisition](acquisition-reports.md)
* [Rapports de comportement](behavior-reports.md)
* [Rapports de conversion](conversions-reports.md)
