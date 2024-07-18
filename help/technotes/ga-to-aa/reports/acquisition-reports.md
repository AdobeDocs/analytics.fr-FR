---
title: Rapports d’acquisition dans Adobe Analytics
description: Découvrez comment créer des rapports basés sur l’acquisition à l’aide d’Analysis Workspace.
feature: Third-party Integration
exl-id: 2929d34b-8eb0-4105-a49c-02d536929fe0
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '1578'
ht-degree: 99%

---

# Rapports d’acquisition

Les rapports d’acquisition vous montrent comment obtenir des visiteurs sur votre site.

Dans Adobe Analytics, ces rapports sont appelés **canaux marketing**. Ils nécessitent une configuration initiale de base, mais permettent une vue beaucoup plus personnalisée des canaux.

>[!IMPORTANT]
>
> Configurez vos règles de traitement des canaux marketing pour utiliser ces rapports. Pour en savoir plus sur la configuration optimale des canaux marketing dans votre entreprise, voir [Prise en main des canaux marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

Cette page part du principe que l’utilisateur maîtrise les bases de l’utilisation d’Analysis Workspace. Voir [Création d’un rapport de base dans Analysis Workspace pour les utilisateurs de Google Analytics](create-report.md) si vous ne connaissez pas encore l’outil dans Adobe Analytics.

## Tout le trafic - Canaux

Affiche une vue globale de tous les canaux utilisés par les visiteurs pour atteindre votre site.

1. Dans le menu Composants, recherchez la dimension **Canal marketing** et faites-la glisser sur la grande zone de tableau à structure libre intitulée « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

## Tout le trafic - Graphiques Treemap

Affiche un graphique Treemap du trafic des canaux. Ce rapport est similaire à Tout le trafic - Canaux, mais il s’affiche différemment.

1. Cliquez sur l’icône Visualisations à gauche et faites glisser la visualisation du graphique Treemap sur l’espace de travail au-dessus du tableau à structure libre.
2. Cliquez sur l’icône Composants à gauche, puis faites glisser la dimension **Canal marketing** et faites-la glisser sur la grande zone de tableau à structure libre intitulée « Déposer une dimension ici ».
3. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).
4. Notez que d’autres mesures créent des graphiques Treemap supplémentaires. Si vous voulez un graphique Treemap unique :
   1. Cliquez sur la cellule supérieure de la mesure de votre choix pour représenter le graphique Treemap.
   2. Maintenez la touche Maj enfoncée et cliquez sur la dernière cellule de cette même colonne de mesure pour mettre la colonne en surbrillance en bleu. Si cette opération est effectuée correctement, un graphique Treemap est présent dans la visualisation.
   3. Cliquez sur le point coloré dans le coin supérieur droit de la visualisation du graphique Treemap, puis cochez la case « Verrouiller la sélection ».

Les graphiques Treemap peuvent être appliqués à n’importe quelle dimension, pas uniquement aux canaux marketing.

## Tout le trafic - Source/Support

Les rapports Source et Support indiquent les domaines qui ont conduit le trafic vers votre site.

* La dimension principale **Source** est disponible dans Analysis Workspace en tant que dimension **Domaine référent**.
* La dimension principale **Support** est disponible dans Analysis Workspace en tant que dimension **Type de référent**.
* La dimension principale **Mot-clé** est disponible dans Analysis Workspace en tant que dimension **Mot-clé de recherche**.

1. Dans le menu Composants, recherchez la dimension de votre choix affichée ci-dessus et faites-la glisser sur la grande zone de tableau à structure libre intitulée « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

Pour plus d’informations sur leurs dimensions respectives, voir les pages suivantes du guide d’utilisation des composants :

* [Domaine référent](/help/components/dimensions/referring-domain.md)
* [Type de référent](/help/components/dimensions/referrer-type.md)
* [Mot-clé de recherche](/help/components/dimensions/search-keyword.md)

## Tout le trafic - Références

* La dimension principale **Source** est disponible dans Analysis Workspace en tant que dimension **Domaine référent**.
* La dimension principale **Page de destination** est disponible dans Analysis Workspace en tant que dimension **Page d’accès**.

1. Dans le menu Composants, recherchez la dimension **Domaine référent** ou **Page d’accès** et faites-la glisser sur la grande zone de tableau à structure libre intitulée « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

Pour plus d’informations sur la dimension [Domaine référent](/help/components/dimensions/referring-domain.md), voir le guide d’utilisation des composants.

## Rapports Google Ads et Google Search Console

Adobe utilise une fonctionnalité d’Analysis Workspace appelée Advertising Analytics pour importer des données de recherche et de publicité provenant de plusieurs plateformes, y compris Google.

La fonction d’analyse des publicités nécessite d’être configurée pour renvoyer des données. Consultez l’[aide d’Advertising Analytics](/help/integrate/c-advertising-analytics/overview.md) pour plus d’informations sur la manière d’activer ces dimensions supplémentaires dans Analysis Workspace.

## Rapports sur les réseaux sociaux

Les rapports sur les réseaux sociaux fournissent des informations similaires aux rapports sur le comportement, pour ce qui est des réseaux sociaux. Ces données sont disponibles dans Analysis Workspace en combinant une dimension à un segment.

Il arrive que des visiteurs arrivent sur votre site par le biais de plusieurs canaux au cours de la même session. Par exemple, un visiteur clique sur une page d’un réseau social, puis, quelques minutes plus tard, passe par un moteur de recherche pour accéder à votre site. Dans ce cas, des domaines qui ne correspondent pas à des réseaux sociaux peuvent apparaître dans ce rapport. Si vous souhaitez exclure des domaines qui ne correspondent pas à des réseaux sociaux, triez le rapport par visites ou créez une copie du segment en fonction des accès et non des visites. Pour plus d’informations, voir [Conteneurs et segmentation](/help/components/segmentation/seg-overview.md) dans le guide d’utilisation des composants.

### Réseaux sociaux - Références réseau

Le rapport Références réseau indique les domaines des réseaux sociaux qui ont conduit le trafic vers votre site. Ces données sont disponibles dans Analysis Workspace à l’aide de la dimension **Domaine référent** et du segment **Visites issues des sites sociaux**.

1. Dans le menu Composants, recherchez la dimension **Domaine référent** et faites-la glisser sur la grande zone de tableau à structure libre intitulée « Déposer une dimension ici ».
2. Dans le menu Composants, recherchez le segment **Visites issues des sites sociaux** et faites-le glisser sur la petite zone de tableau à structure libre intitulée « Déposer un segment ici ».
3. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

### Réseaux sociaux - Pages de destination

Le rapport Pages de destination indique les pages sur lesquelles les visiteurs sont arrivés après avoir cliqué sur un lien sur un réseau social. Ces données sont disponibles dans Analysis Workspace à l’aide de la dimension **Page d’accès** et du segment **Visites issues des sites sociaux**.

1. Dans le menu Composants, recherchez la dimension **Page d’accès** et faites-la glisser sur la grande zone de tableau à structure libre intitulée « Déposer une dimension ici ».
2. Dans le menu Composants, recherchez le segment **Visites issues des sites sociaux** et faites-le glisser sur la petite zone de tableau à structure libre intitulée « Déposer un segment ici ».
3. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

### Réseaux sociaux - Conversions

Le rapport Conversions montre les données de commerce électronique dans le contexte des réseaux sociaux. Une implémentation supplémentaire est nécessaire pour utiliser ces rapports sur les deux plateformes. Adobe conseille de travailler avec un conseiller en implémentation pour s’assurer que ces données sont correctement configurées pour Analysis Workspace.

### Réseaux sociaux - Modules externes

Le rapport Modules externes montre comment les visiteurs interagissent avec les modules externes de médias sociaux intégrés à votre site. Une mise en œuvre supplémentaire est requise pour une utilisation dans Analysis Workspace. Adobe conseille de travailler avec un consultant en mise en œuvre pour assurer la collecte précise de ces données.

### Réseaux sociaux - Flux d’utilisateurs

Le rapport Flux d’utilisateurs affiche les données de cheminement dans le contexte des visiteurs qui arrivent par le biais d’un réseau social.

1. Cliquez sur l’icône Visualisations à gauche, puis faites glisser une visualisation de flux sur l’espace de travail situé au-dessus du tableau à structure libre.
2. Cliquez sur l’icône Composants à gauche, puis faites glisser le segment **Visites issues des sites sociaux** sur la petite zone de tableau à structure libre intitulée « Déposer un segment ici ».
3. Recherchez la dimension **Pages**, puis cliquez sur l’icône en forme de flèche pour afficher les valeurs de page. Les éléments de dimension sont en jaune.
4. Recherchez la valeur de page de votre choix et faites-la glisser sur l’espace « Dimension ou élément » au centre.
5. Ce rapport de flux est interactif. Cliquez sur l’une des valeurs pour étendre les flux aux pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.

## Campagnes - Toutes

Le rapport des campagnes est disponible dans Analysis Workspace à l’aide de la dimension **Code de suivi**. Notez que l’utilisation de la dimension Code de suivi nécessite une implémentation supplémentaire pour collecter les données.

Il est possible de collecter des paramètres UTM dans Adobe Analytics à l’aide de variables personnalisées (eVars). Adobe recommande de travailler avec un conseiller en implémentation pour s’assurer que les valeurs de code de suivi sont collectées avec précision dans Adobe Analytics.

1. Dans le menu Composants, recherchez la dimension **Code de suivi** et faites-la glisser sur la grande zone de tableau à structure libre intitulée « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

## Campagnes - Mots-clés payants

Le rapport Mots-clés payants montre la façon dont chaque mot-clé se comporte après qu’un visiteur a cliqué sur un lien de référencement payant à partir d’un moteur de recherche. La dimension **Mots-clés de recherche - Payée** est disponible dans Analysis Workspace, mais nécessite une configuration unique de la détection de référencement payant pour collecter les données. Pour plus d’informations sur la configuration, voir [Détection de référencement payant](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md) dans le guide d’utilisation destiné à l’administrateur.

1. Dans le menu Composants, recherchez la dimension **Mots-clés de recherche - Payée** et faites-la glisser sur la grande zone de tableau à structure libre intitulée « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

## Campagnes - Mots-clés organiques

Le rapport Mots-clés organiques montre la façon dont chaque mot-clé se comporte après qu’un visiteur a cliqué sur un lien de référencement naturel à partir d’un moteur de recherche. La dimension **Mots-clés de recherche - Naturelle** est disponible dans Analysis Workspace. Notez que si la détection de référencement payant n’est pas configurée, cette dimension collecte à la fois les mots-clés payants et naturels.

1. Dans le menu Composants, recherchez la dimension **Mots-clés de recherche - Naturelle** et faites-la glisser sur la grande zone de tableau à structure libre intitulée « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

## Analyse des coûts

Ce rapport présente les données sur les visites, les coûts et les recettes pour vos canaux marketing payants. Adobe fournit un produit dédié appelé Adobe Advertising Cloud. Si votre entreprise souhaite utiliser ce produit, contactez votre équipe de compte d’Adobe.
