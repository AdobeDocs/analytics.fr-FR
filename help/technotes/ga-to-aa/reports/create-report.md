---
title: Création d’un rapport de base dans Analysis Workspace
description: Découvrez comment créer un rapport de base dans Analysis Workspace dans un format adapté aux utilisateurs habitués aux outils tiers tels que Google Analytics.
feature: Third-party Integration
exl-id: 513da3f1-ad24-4d5b-bc35-dbcd3694cbdf
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 100%

---

# Création d’un rapport de base dans Analysis Workspace pour les utilisateurs de Google Analytics

Analysis Workspace (l’une des principales fonctionnalités d’Adobe Analytics) fournit aux utilisateurs un espace robuste dans lequel obtenir des informations sur les données collectées. La création de rapports est très différente dans Google Analytics et Adobe Analytics :

* La structure des rapports dans Google Analytics permet de sélectionner un type particulier de données, comme la géolocalisation ou le trafic de référence. La plateforme utilise une vue de création de rapports préfabriquée en fonction de la meilleure manière prévue d’afficher ces données.
* La structure des rapports dans Analysis Workspace offre un canevas vierge et donc plus de souplesse pour répondre aux besoins exacts en termes de création de rapports.

Comme Analysis Workspace fonctionne plutôt comme un canevas au lieu de proposer des rapports préfabriqués, recréer des rapports à partir de Google Analytics consiste simplement à utiliser les visualisations et composants adaptés.

## Termes clés utilisés dans Workspace

* Les **panneaux** sont les principaux blocs de création de l’espace de travail. Dans presque tous les scénarios, un panneau à structure libre est utilisé.
* Les **visualisations** constituent tous les panneaux à structure libre. Leur but est de représenter les données en différents formats. Ce format est souvent un tableau, mais il peut aussi s’agir d’un graphique en anneau ou en courbes. De nombreux rapports dans Google Analytics sont constitués de l’équivalent de deux visualisations : un graphique en courbes et un tableau à structure libre.
* Les **composants** sont placés dans une visualisation pour renvoyer des données. Les composants peuvent être mélangés de différentes manières pour répondre aux besoins de création de rapports.
   * Les **dimensions** sont des valeurs de variable et contiennent généralement du texte. Il peut s’agir d’un nom de page, d’un référent ou d’un pays géographique. Elles sont généralement répertoriées sous forme de lignes dans un tableau.
   * Les **mesures** désignent généralement un type d’événement ou de conversion. Il peut s’agir d’événements courants comme une page vue ou plus importants comme un achat ou un enregistrement. Elles apparaissent généralement sous forme de colonnes dans des tableaux pour indiquer le nombre de fois qu’un événement s’est produit par dimension.
   * Les **segments** sont un sous-ensemble de vos données et se comportent comme les segments dans Google Analytics. Ils vous permettent de créer des filtres personnalisés pour vous concentrer sur une partie spécifique de vos données.
   * Les **périodes** permettent d’organiser les données selon la date de l’événement. Elles constituent la colonne vertébrale de l’affichage des tendances au fil du temps et sont souvent associées à une mesure.

## Création d’un rapport de base dans Workspace

Créez un rapport Toutes les pages (similaire à celui de Google Analytics) en faisant glisser les composants appropriés sur un canevas d’espace de travail.

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur l’icône à 9 carrés dans le coin supérieur droit, puis sur le logo Analytics coloré.
1. Dans la barre de navigation supérieure, cliquez sur Workspace.
1. Cliquez sur le bouton « Créer un projet ».
1. Dans la fenêtre contextuelle modale, assurez-vous que l’option « Projet vierge » est sélectionnée, puis cliquez sur Créer.
1. À gauche, une liste de dimensions, mesures, segments et périodes s’affiche. Recherchez la dimension Pages (en orange), puis faites-la glisser sur le canevas « Déposer une dimension ici ».
1. Un rapport montrant les principales pages du mois s’affiche. Analysis Workspace renseigne automatiquement la mesure [Occurrences](/help/components/metrics/occurrences.md) dans le rapport.
1. Un tableau Google Analytics contient généralement 7 à 8 mesures. Recherchez la mesure Taux de rebonds (en vert) et faites-la glisser en regard de l’en-tête de mesure Occurrences. Si vous faites glisser la mesure Taux de rebond en regard de la mesure Occurrences, les deux mesures s’affichent côte à côte.
1. De nombreuses mesures peuvent être placées côte à côte en faisant glisser les mesures en regard des en-têtes de mesure existants. Pour plus d’informations sur la manière d’obtenir des mesures généralement utilisées dans Google Analytics, voir [Mesures fréquemment utilisées](common-metrics.md).

   ![Nouvelle mesure](/help/technotes/ga-to-aa/assets/new_metric.png)

## Début avec un modèle de rapport préconfiguré dans Workspace

Créez le modèle Consommation de contenu (similaire au rapport Toutes les pages dans Google Analytics) en accédant à un modèle de projet.

1. Cliquez sur le bouton « Créer un projet ».
1. Recherchez l’icône « Consommation de contenu (web) » répertoriée sous Tous les modèles et cliquez deux fois dessus.
1. Parcourez chacune des visualisations préconfigurées : flux de page d’accès, tableau des pages principales, flux de page de sortie, flux de section d’entrée sur le site et tableau des principales sections du site.

   ![Sélection de modèle](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## Tester l’outil

Analysis Workspace étant un outil de reporting, il n’a aucun impact sur la collecte de données. Il n’y a aucune répercussion si vous faites glisser sans distinction des composants dans un projet pour voir ce qui fonctionne. Faites glisser différentes combinaisons de dimensions et de mesures dans votre projet Workspace pour voir ce qui est mis à votre disposition.

Si vous faites glisser accidentellement un composant non valide vers votre projet Workspace ou souhaitez revenir en arrière d’une étape, appuyez sur ctrl + Z (Windows) ou sur cmd + Z (Mac) pour annuler la dernière action effectuée. Vous pouvez également commencer à zéro en cliquant sur *[!UICONTROL Projet] > [!UICONTROL Nouveau]* dans le menu supérieur gauche.

Adobe a placé de nombreuses fonctionnalités d’Analysis Workspace dans le menu contextuel accessible par un clic droit. Il est possible d’effectuer un clic droit sur la plupart des visualisations et composants pour obtenir une analyse ou effectuer des interactions plus détaillées. Pensez à cliquer avec le bouton droit de la souris sur les composants de votre espace de travail pour voir quelles options sont disponibles.

## Les dimensions et mesures à utiliser

Si vous êtes à l’aise avec Analysis Workspace et souhaitez recréer un rapport spécifique généralement affiché dans Google Analytics, recherchez le rapport sur sa page respective :

* [Rapports en temps réel](realtime-reports.md)
* [Rapports d’audience](audience-reports.md)
* [Rapports d’acquisition](acquisition-reports.md)
* [Rapports de comportement](behavior-reports.md)
* [Rapports de conversion](conversions-reports.md)
