---
title: Rapports de comportement dans Adobe Analytics
description: Découvrez comment créer des rapports de comportement dans Adobe Analytics
translation-type: tm+mt
source-git-commit: e1cbdf87140b915dccbb8f64694797bb903d8ab8

---


# Rapports de comportement

Les rapports de comportement affichent des informations sur la manière dont les utilisateurs interagissent avec votre site.

Cette page suppose que l’utilisateur a une connaissance de base de l’utilisation d’Analysis Workspace. Voir [Création d’un rapport de base dans Analysis Workspace pour les utilisateurs](create-report.md) de Google Analytics si vous ne connaissez pas encore l’outil dans Adobe Analytics.

## Flux de comportement

Le rapport Flux de comportement peut être recréé à l’aide de la visualisation Flux.

1. Cliquez sur l’icône de visualisation à gauche, puis faites glisser une visualisation Flux sur l’espace de travail au-dessus du tableau à structure libre.
2. Recherchez la dimension **Page** , puis cliquez sur l’icône de flèche pour afficher les valeurs de page. Les valeurs de dimension sont colorées en jaune.
3. Localisez la valeur de page de votre choix et faites-la glisser dans l’espace &quot;Dimension ou élément&quot; au centre.
4. Ce rapport de flux est interactif. Cliquez sur l’une des valeurs pour étendre les flux aux pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.

![Rapport Flux](/help/technotes/ga-to-aa/assets/flow.png)

## Contenu du site - Toutes les pages

Le rapport Pages montre les performances de pages individuelles sur votre site.

1. Dans le menu Composants, recherchez la dimension **Pages** et faites-la glisser sur la grande zone de tableau à structure libre intitulée &quot;Déposer une dimension ici&quot;.
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

Adobe propose également plusieurs espaces de travail précréés appelés modèles. Le modèle Consommation de contenu (Web) fournit une valeur similaire au rapport Toutes les pages.

1. Cliquez sur *[!UICONTROL Projet]>[!UICONTROL Nouveau]*, ce qui ouvre une fenêtre modale avec des options de projet.
2. Cliquez sur le modèle Consommation de contenu (Web), puis sur Créer.

## Contenu du site - Analyse du contenu

Le rapport d’analyse du contenu vous permet d’examiner le trafic des pages par structure d’URL. Une mise en oeuvre supplémentaire est requise pour une utilisation dans Analysis Workspace. Adobe recommande de travailler avec un conseiller en implémentation pour s’assurer que ces données sont collectées avec précision.

## Contenu du site - Pages d’entrée

Le rapport Pages d’entrée affiche les principales pages d’entrée de votre site. Les pages d’entrée sont disponibles dans Analysis Workspace en tant que dimension Page **d’** entrée.

1. Dans le menu Composants, recherchez la dimension Page **d’** entrée et faites-la glisser sur la grande zone de tableau à structure libre intitulée &quot;Déposer une dimension ici&quot;.
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

Adobe recommande d’utiliser la mesure **Visites** pour cette dimension.

## Contenu du site - Pages de sortie

Le rapport Pages de sortie montre les pages principales qui sont devenues la dernière page d’une visite individuelle. Il est disponible dans Analysis Workspace sous le même nom.

1. Dans le menu Composants, recherchez la dimension Page **de** sortie et faites-la glisser sur la grande zone de tableau à structure libre intitulée &quot;Déposer une dimension ici&quot;.
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

Adobe recommande d’utiliser la mesure **Visites** pour cette dimension.

## Rapports Vitesse du site

Les rapports de vitesse du site indiquent la vitesse de chargement des pages, ce qui vous permet d&#39;augmenter les temps de chargement des pages.

Cette fonctionnalité nécessite une implémentation supplémentaire sur les deux plates-formes ; Adobe conseille de travailler avec un conseiller en implémentation pour s’assurer que ces données sont correctement configurées pour Analysis Workspace. Le module externe [getPageLoadTime](/help/implement/vars/plugins/getpageloadtime.md) est généralement affecté à une eVar pour obtenir des données de performances dans Adobe Analytics.

## Rapports de recherche de site

Les rapports de recherche de site fournissent des informations sur la manière dont les visiteurs utilisent les fonctionnalités de recherche interne de votre site.

Cette fonctionnalité nécessite une implémentation supplémentaire sur les deux plates-formes ; Adobe conseille de travailler avec un conseiller en implémentation pour s’assurer que ces données sont correctement configurées pour Analysis Workspace. En règle générale, un terme de recherche interne est extrait d’un paramètre de chaîne de requête et placé dans une eVar pour la création de rapports.

## Rapports d’événements

Les événements présentent des différences structurelles majeures entre Google et Adobe Analytics. Les deux nécessitent des modifications d’implémentation supplémentaires pour fonctionner correctement sur leur plateforme respective.

* Dans Google Analytics, les événements sont définis comme du texte dans votre implémentation. Les événements comportent des catégories, des actions et des libellés.
* Dans Adobe Analytics, les événements sont d’abord configurés dans la console d’administration où un identifiant est affecté. Cet identifiant est utilisé dans le code d’implémentation. Par exemple :
   1. Vous pouvez définir event1 dans la console d’administration comme &quot;Inscriptions&quot;.
   2. Dans votre implémentation, vous devez inclure event1 dans la variable events de la page de confirmation de l’enregistrement. Chaque fois que la page de confirmation d’inscription est affichée, event1 augmente.
   3. Dans Analysis Workspace, l’option &quot;Inscriptions&quot; apparaît comme une mesure à utiliser dans n’importe quel rapport.

Comme cette fonctionnalité nécessite des modifications de mise en oeuvre, Adobe conseille de travailler avec un conseiller en implémentation pour s’assurer que les données sont correctement configurées pour Analysis Workspace.

## Rapports de l’éditeur

Tout comme Google requiert une connexion avec Google Ad Manager, Adobe propose un produit dédié pour fournir des informations appelé Adobe Advertising Cloud. Si votre entreprise souhaite utiliser ce produit, contactez son gestionnaire de compte.
