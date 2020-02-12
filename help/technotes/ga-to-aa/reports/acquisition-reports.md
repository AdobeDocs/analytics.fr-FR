---
title: Rapports d’acquisition dans Adobe Analytics
description: Découvrez comment créer des rapports basés sur l’acquisition à l’aide d’Analysis Workspace.
translation-type: tm+mt
source-git-commit: 0d9d94608deac089bed97f7570b468e098d1b46e

---


# Rapports d’acquisition

Les rapports d’acquisition montrent comment obtenir des visiteurs sur votre site.

Dans Adobe Analytics, ces rapports sont appelés canaux **marketing**. Ils nécessitent une configuration initiale de base, mais permettent une vue beaucoup plus personnalisée des canaux.

> [!IMPORTANT]
>
> Configurez vos règles de traitement Canal marketing pour utiliser ces rapports. Voir [Prise en main des canaux](/help/components/c-marketing-channels/getting-started/c-getting-started-mchannel.md) marketing pour plus d’informations sur la configuration optimale des canaux marketing dans votre entreprise.

Cette page suppose que l’utilisateur a une connaissance de base de l’utilisation d’Analysis Workspace. Voir [Création d’un rapport de base dans Analysis Workspace pour les utilisateurs](create-report.md) de Google Analytics si vous ne connaissez pas encore l’outil dans Adobe Analytics.

## Tout le trafic - Canaux

Affiche une vue globale de tous les canaux utilisés par les visiteurs pour atteindre votre site.

1. Dans le menu Composants, recherchez la dimension Canal **** marketing et faites-la glisser sur la grande zone de tableau à structure libre intitulée &quot;Déposer une dimension ici&quot;.
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

## Tout le trafic - Treemaps

Affiche un triangle du trafic des canaux. Ce rapport est similaire à l’ensemble du trafic - Canaux, mais il s’affiche différemment.

1. Cliquez sur l’icône Visualisations sur la gauche, puis faites glisser la visualisation Treemap sur l’espace de travail au-dessus du tableau à structure libre vide.
2. Cliquez sur l’icône Composants sur la gauche, puis faites glisser la dimension Canal **** marketing sur la grande zone de tableau à structure libre intitulée &quot;Déposez une dimension ici&quot;.
3. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.
4. Notez que d’autres mesures créent des treemaps supplémentaires. Si un seul Treemap est souhaité :
   1. Cliquez sur la cellule supérieure de la mesure de votre choix pour représenter le mappage de segment.
   2. Maintenez la touche Maj enfoncée et cliquez sur la dernière cellule de cette même colonne de mesure pour mettre la colonne en surbrillance en bleu. Si cette opération est effectuée correctement, un Treemap est présent dans la visualisation.
   3. Cliquez sur le point coloré dans le coin supérieur droit de la visualisation de la carte Treemap, puis cochez la case &quot;Verrouiller la sélection&quot;.

Les Treemaps peuvent être appliqués à n’importe quelle dimension, et pas seulement aux canaux marketing.

## Tout le trafic - Source/Moyen

Les rapports Source et Moyen indiquent les domaines qui ont conduit le trafic vers votre site.

* La dimension principale **Source** est disponible dans Analysis Workspace en tant que dimension de domaine **** référent.
* La dimension primaire **moyenne** est disponible dans Analysis Workspace en tant que dimension Type **de** référent.
* La dimension principale Mot- **clé** est disponible dans Analysis Workspace en tant que dimension Mot-clé **de** recherche.

1. Dans le menu des composants, recherchez la dimension souhaitée mentionnée ci-dessus et faites-la glisser sur la grande zone de tableau à structure libre intitulée &quot;Déposez une dimension ici&quot;.
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

Pour plus d’informations sur leurs dimensions respectives, consultez les pages suivantes du guide de l’utilisateur Composants :

* [Domaine référent](/help/components/c-variables/dimensionslist/reports-referring-domains.md)
* [Type de référent](/help/components/c-variables/dimensionslist/reports-ref-types.md)
* [Mot-clé de recherche](/help/components/c-variables/dimensionslist/reports-search-keywords.md)

## Tout le trafic - Références

* La dimension principale **Source** est disponible dans Analysis Workspace en tant que dimension de domaine **** référent.
* La dimension principale **de la page** d’entrée est disponible dans Analysis Workspace en tant que dimension de page **d’** entrée.

1. Dans le menu des composants, recherchez la dimension Domaine **** référent ou Page **d’** entrée et faites-la glisser sur la grande zone de tableau à structure libre intitulée &quot;Déposez une dimension ici&quot;.
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

Pour plus d’informations, voir la dimension Domaine [de](/help/components/c-variables/dimensionslist/reports-referring-domains.md) référence dans le guide de l’utilisateur Composants.

## Rapports Publicités Google et rapports Console de recherche

Adobe utilise une fonctionnalité d’Analysis Workspace appelée Analytics de publicité pour importer des données de recherche et de publicité provenant de plusieurs plateformes, y compris Google.

La fonction d’analyse des publicités nécessite une configuration pour renvoyer des données. Voir l’aide [d’Analytics](/help/integrate/c-advertising-analytics/overview.md) de publicité pour en savoir plus sur la manière d’activer ces dimensions supplémentaires dans Analysis Workspace.

## Rapports sur les réseaux sociaux

Les rapports sur les réseaux sociaux fournissent des informations similaires aux rapports sur le comportement, sauf dans le contexte des réseaux sociaux. Ces données sont disponibles dans Analysis Workspace en combinant une dimension à un segment.

Il arrive que des visiteurs arrivent sur votre site par le biais de plusieurs canaux au cours de la même session. Par exemple, un visiteur clique sur une page de médias sociaux, puis, quelques minutes plus tard, visite un moteur de recherche pour accéder à votre site. Dans ce cas, les domaines non sociaux peuvent apparaître dans ce rapport. Si vous souhaitez exclure des domaines non sociaux, triez le rapport par visites ou créez une copie du segment en fonction des accès et non des visites. Pour plus d’informations, voir Conteneurs [de](/help/components/c-segmentation/seg-overview.md) segmentation dans le guide de l’utilisateur Composants.

### Social - Références réseau

Le rapport Références réseau indique les domaines de réseau social qui ont conduit le trafic vers votre site. Ces données sont disponibles dans Analysis Workspace à l’aide de la dimension Domaine **** référent et du segment **Visites à partir de sites** sociaux.

1. Dans le menu Composants, recherchez la dimension Domaine **de** référence et faites-la glisser sur la grande zone de tableau à structure libre intitulée &quot;Déposer une dimension ici&quot;.
2. Dans le menu Composants, recherchez le segment **Visites à partir de sites** sociaux et faites glisser le curseur sur la petite zone située juste au-dessus du tableau à structure libre intitulé &quot;Faire glisser un segment ici&quot;.
3. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

### Social - Pages d’entrée

Le rapport Pages d’entrée indique les pages sur lesquelles les visiteurs sont arrivés après avoir cliqué sur un lien sur un réseau social. Ces données sont disponibles dans Analysis Workspace à l’aide de la dimension Page **d’** entrée et **Visites à partir du segment Sites** sociaux.

1. Dans le menu Composants, recherchez la dimension Page **d’** entrée et faites-la glisser sur la grande zone de tableau à structure libre intitulée &quot;Déposer une dimension ici&quot;.
2. Dans le menu Composants, recherchez le segment **Visites à partir de sites** sociaux et faites glisser le curseur sur la petite zone située juste au-dessus du tableau à structure libre intitulé &quot;Faire glisser un segment ici&quot;.
3. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

### Social - Conversions

Le rapport Conversions montre les données de commerce électronique dans le contexte des réseaux sociaux. Une implémentation supplémentaire est nécessaire pour utiliser ces rapports sur les deux plateformes ; Adobe conseille de travailler avec un conseiller en implémentation pour s’assurer que ces données sont correctement configurées pour Analysis Workspace.

### Social - Modules externes

Le rapport Modules externes montre comment les visiteurs interagissent avec les modules externes de médias sociaux intégrés de votre site. Une mise en oeuvre supplémentaire est requise pour une utilisation dans Analysis Workspace. Adobe recommande de travailler avec un conseiller en implémentation pour s’assurer que ces données sont collectées avec précision.

### Social - Flux d’utilisateurs

Le rapport de flux Utilisateurs affiche les données de cheminement dans le contexte des visiteurs qui arrivent par le biais d’un réseau social.

1. Cliquez sur l’icône de visualisation à gauche, puis faites glisser une visualisation Flux sur l’espace de travail au-dessus du tableau à structure libre.
2. Cliquez sur l’icône Composants sur la gauche, puis faites glisser le segment **Visites depuis les sites** sociaux sur la petite zone située juste au-dessus de la visualisation du flux intitulée &quot;Faire glisser un segment ici&quot;.
3. Recherchez la dimension **Pages** , puis cliquez sur l’icône de flèche pour afficher les valeurs de page. Les valeurs de dimension sont colorées en jaune.
4. Localisez la valeur de page de votre choix et faites-la glisser dans l’espace &quot;Dimension ou élément&quot; au centre.
5. Ce rapport de flux est interactif. Cliquez sur l’une des valeurs pour étendre les flux aux pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.

## Campagnes - Toutes

Le rapport des campagnes est disponible dans Analysis Workspace à l’aide de la dimension Code **de** suivi. Notez que l’utilisation de la dimension Code de suivi nécessite une implémentation supplémentaire pour collecter les données.

Il est possible de collecter des paramètres UTM dans Adobe Analytics à l’aide de variables personnalisées (eVars). Adobe recommande de travailler avec un conseiller en implémentation pour s’assurer que les valeurs de code de suivi sont collectées avec précision dans Adobe Analytics.

1. Dans le menu Composants, recherchez la dimension Code **de** suivi et faites-la glisser sur la grande zone de tableau à structure libre intitulée &quot;Déposer une dimension ici&quot;.
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

## Campagnes - Mots-clés payés

Le rapport Mots-clés payés montre comment chaque mot-clé se comporte après qu&#39;un visiteur a cliqué sur un lien de recherche payante à partir d&#39;un moteur de recherche. La dimension Mots-clés de **recherche - Payée** est disponible dans Analysis Workspace, mais nécessite une configuration unique de la détection de recherche payante pour collecter les données. Pour plus d’informations sur la configuration, voir Détection [](/help/admin/admin/paid-search-detection/paid-search-detection.md) de recherche payante dans le guide de l’utilisateur Admin.

1. Dans le menu Composants, recherchez la dimension Mot-clé de **recherche - Payante** et faites-la glisser sur la grande zone de tableau à structure libre intitulée &quot;Déposer une dimension ici&quot;.
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

## Campagnes - Mots-clés organiques

Le rapport Mots-clés organiques montre les performances de chaque mot-clé après qu&#39;un visiteur a cliqué sur un lien de recherche organique à partir d&#39;un moteur de recherche. La dimension Mots-clés de **recherche - Naturelle** est disponible dans Analysis Workspace. Notez que si la détection de recherche payante n’est pas configurée, cette dimension collecte les mots-clés payants et naturels.

1. Dans le menu Composants, recherchez la dimension Mot-clé de **recherche - Naturelle** et faites-la glisser sur la grande zone de tableau à structure libre intitulée &quot;Déposer une dimension ici&quot;.
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

## Analyse des coûts

Ce rapport présente les données sur les visites, les coûts et les recettes pour vos canaux marketing payants. Adobe fournit un produit dédié à Adobe Advertising Cloud. Si votre entreprise souhaite utiliser ce produit, contactez son gestionnaire de compte.
