---
title: Rapports de comportement dans Adobe Analytics
description: Découvrez comment créer des rapports de comportement dans Adobe Analytics
translation-type: ht
source-git-commit: e1cbdf87140b915dccbb8f64694797bb903d8ab8

---


# Rapports de comportement

Les rapports de comportement montrent des informations sur la manière dont les utilisateurs interagissent avec votre site.

Cette page part du principe que l’utilisateur maîtrise les bases de l’utilisation d’Analysis Workspace. Voir [Création d’un rapport de base dans Analysis Workspace pour les utilisateurs de Google Analytics](create-report.md) si vous ne connaissez pas encore l’outil dans Adobe Analytics.

## Flux de comportement

Le rapport Flux de comportement peut être recréé à l’aide de la visualisation de flux.

1. Cliquez sur l’icône Visualisations à gauche, puis faites glisser une visualisation de flux sur l’espace de travail situé au-dessus du tableau à structure libre.
2. Recherchez la dimension **Page**, puis cliquez sur l’icône de flèche pour afficher les valeurs de page. Les valeurs de dimension sont en jaune.
3. Recherchez la valeur de page de votre choix et faites-la glisser sur l’espace « Dimension ou élément » au centre.
4. Ce rapport de flux est interactif. Cliquez sur l’une des valeurs pour étendre les flux aux pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.

![Rapport de flux](/help/technotes/ga-to-aa/assets/flow.png)

## Contenu du site - Toutes les pages

Le rapport de pages montre les performances de pages individuelles sur votre site.

1. Dans le menu Composants, recherchez la dimension **Pages** et faites-la glisser sur la grande zone de tableau à structure libre « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

Adobe propose également plusieurs espaces de travail précréés appelés modèles. Le modèle Consommation de contenu (web) fournit une valeur similaire au rapport Toutes les pages.

1. Cliquez sur *[!UICONTROL Projet] >[!UICONTROL Nouveau]* pour ouvrir une fenêtre modale incluant les options du projet.
2. Cliquez sur le modèle Consommation de contenu (web), puis sur Créer.

## Contenu du site - Analyse en profondeur du contenu

Le rapport Analyse en profondeur du contenu vous permet d’examiner le trafic d’une page en fonction de la structure de l’URL. Une mise en œuvre supplémentaire est requise pour une utilisation dans Analysis Workspace. Adobe conseille de travailler avec un consultant en mise en œuvre pour assurer la collecte précise de ces données.

## Contenu du site - Pages d’entrée

Le rapport Pages d’accueil montre les principales pages d’accueil sur votre site. Les pages d’accueil sont disponibles dans Analysis Workspace comme dimension de **Page d’accès**.

1. Dans le menu Composants, recherchez la dimension **Page d’accès** et faites-la glisser sur la grande zone de tableau à structure libre « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

Adobe conseille d’utiliser la mesure **Visites** pour cette dimension.

## Contenu du site - Pages de sortie

Le rapport Pages de sortie montre quelle page principale est la dernière page visitée par un utilisateur. Il est disponible sous le même nom dans Analysis Workspace.

1. Dans le menu Composants, recherchez la dimension **Page de sortie** et faites-la glisser sur la grande zone de tableau à structure libre « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

Adobe conseille d’utiliser la mesure **Visites** pour cette dimension.

## Rapports de vitesse de site

Les rapports de vitesse de site montrent la vitesse de chargement des pages, ce qui vous permet d’améliorer les temps de chargement de vos pages.

Cette fonctionnalité nécessite une mise en œuvre supplémentaire sur les deux plateformes. Adobe conseille de travailler avec un conseiller en mise en œuvre pour que ces données soient correctement configurées pour Analysis Workspace. Le module [getPageLoadTime](/help/implement/vars/plugins/getpageloadtime.md) est généralement affecté à une eVar pour obtenir des données de performances dans Adobe Analytics.

## Rapports de recherche de site

Les rapports de recherche de site fournissent des informations sur la manière dont les visiteurs utilisent les fonctionnalités de recherche interne de votre site.

Cette fonctionnalité nécessite une mise en œuvre supplémentaire sur les deux plateformes. Adobe conseille de travailler avec un conseiller en mise en œuvre pour que ces données soient correctement configurées pour Analysis Workspace. En général, un terme de recherche interne est extrait d’un paramètre de chaîne de requête et placé dans une eVar pour la création de rapports.

## Rapports d’événements

Les événements présentent d’importantes différences structurelles entre Google et Adobe Analytics. Les deux nécessitent des modifications de mise en œuvre supplémentaires pour fonctionner correctement sur leur plateforme respective.

* Dans Google Analytics, les événements sont définis comme du texte dans votre mise en œuvre. Les événements comportent des catégories, des actions et des libellés.
* Dans Adobe Analytics, les événements sont d’abord configurés dans l’Admin Console, où un identifiant leur est affecté. Cet identifiant est utilisé dans le code de mise en œuvre. Par exemple :
   1. Vous pouvez définir event1 comme « Inscriptions » dans l’Admin Console.
   2. Dans votre mise en œuvre, incluez event1 dans la variable d’événements de la page de confirmation d’enregistrement. Chaque fois que la page de confirmation d’inscription s’affiche, event1 augmente.
   3. Dans Analysis Workspace, « Inscriptions » apparaît comme une mesure à utiliser dans n’importe quel rapport.

Comme cette fonctionnalité nécessite des modifications de mise en œuvre, Adobe conseille de travailler avec un conseiller en mise en œuvre afin que les données soient correctement configurées pour Analysis Workspace.

## Rapports de l’éditeur

Tout comme Google requiert une connexion avec Google Ad Manager, Adobe propose un produit dédié pour fournir des informations appelé Adobe Advertising Cloud. Si votre organisation souhaite utiliser ce produit, contactez votre gestionnaire de compte.
