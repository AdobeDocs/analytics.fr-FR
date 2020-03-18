---
title: Rapports d’audience dans Adobe Analytics
description: Découvrez comment créer des rapports basés sur les audiences à l’aide d’Analysis Workspace.
translation-type: ht
source-git-commit: 6217430bf0ae9c0f9c6426e4bb2a8101257068e7

---


# Rapports d’audience

Les rapports d’audience montrent des informations sur les types de personnes qui visitent votre site.

Cette page part du principe que l’utilisateur maîtrise les bases de l’utilisation d’Analysis Workspace. Voir [Création d’un rapport de base dans Analysis Workspace pour les utilisateurs de Google Analytics](create-report.md) si vous ne connaissez pas encore l’outil dans Adobe Analytics.

## Utilisateurs actifs

Les utilisateurs actifs montrent le nombre cumulé d’utilisateurs qui se sont connectés à votre site au cours des 1, 7, 14 ou 28 jours précédents. Bien qu’Adobe ne connaisse pas le calcul exact employé par Google Analytics, vous pouvez utiliser la mesure Visiteur unique pour obtenir le compte dédupliqué des utilisateurs qui se sont connectés à votre site sur la période sélectionnée.

Pour obtenir un graphique linéaire des visiteurs uniques, suivez les étapes ci-dessous :

1. Cliquez sur l’icône Visualisations à gauche, puis faites glisser la visualisation de ligne sur l’espace de travail situé au-dessus du tableau à structure libre vide.
2. Cliquez sur l’icône Composants à gauche, puis faites glisser la mesure **Visiteurs uniques** sur le petit espace « Déposer une mesure ici ».
3. Si vous souhaitez une granularité différente, faites glisser la période souhaitée (par exemple **Jour**, **Semaine**, **Mois**, etc.) au-dessus de l’en-tête de dimension de date existant.

Voir [Visiteurs uniques](/help/components/c-variables/c-metrics/metrics-unique-visitors.md) dans le guide d’utilisation des composants pour plus de détails sur la manière dont Adobe calcule les visiteurs uniques.

## Valeur de durée de vie

La valeur de durée de vie est une fonctionnalité qui nécessite une mise en œuvre spécialisée supplémentaire sur les deux plateformes. Adobe conseille de travailler avec un consultant en mise en œuvre pour obtenir ces données.

## Analyse des cohortes

L’analyse des cohortes indique à quelle fréquence les mêmes utilisateurs reviennent sur votre site.

Pour créer un tableau de cohortes :

1. Cliquez sur l’icône Visualisations à gauche, puis faites glisser la visualisation de tableau de cohortes sur l’espace de travail.
2. Cliquez sur l’icône Composants à gauche, puis faites glisser la mesure **Visites** sur les critères d’inclusion et de retour.
3. Cliquez sur Créer.

Pour de plus amples détails sur les personnalisations supplémentaires de la visualisation de cohortes, voir [Analyse des cohortes](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) dans le guide d’utilisation d’Analysis Workspace.

## Audiences

Le rapport Audiences dans Google Analytics nécessite la configuration des audiences. Les audiences nécessitent aussi une configuration dans Adobe via Adobe Audience Manager. Pour plus d’informations, voir le guide d’utilisation d’Adobe Audience Manager.

## Explorateur d’utilisateurs

Le rapport d’explorateur d’utilisateurs permet à un analyste d’afficher des visites individuelles au moyen d’identifiants anonymes. Adobe n’utilise pas les identifiants d’arrière-plan en dehors des flux de données, qui sont des exportations brutes de données au niveau de l’accès.

* Si ces données doivent être utilisées dans Analysis Workspace, il est possible de collaborer avec un consultant en mise en œuvre pour transmettre la valeur du cookie d’identifiant unique anonyme dans une eVar. Notez que cela ne fonctionne qu’avec des mises en œuvre de petite taille incluant moins d’un million de visiteurs uniques par mois.
* Si ces données doivent être utilisées dans des flux de données, les colonnes concaténées `visid_high` et `visid_low` constituent la méthode la plus courante d’identification des visiteurs uniques. Pour en savoir plus sur les [Flux de données](/help/export/analytics-data-feed/data-feed-overview.md), voir le guide d’utilisation de l’exportation.

## Rapports de démographie et d’intérêts

Les données de démographie et d’intérêt fournissent des informations sur l’âge, le sexe et les intérêts des utilisateurs du site. Ces données sont collectées par Google via ses fonctionnalités de suivi inter-sites.

Les données de démographie et d’intérêt ne sont pas automatiquement collectées par Adobe. Toutefois, si votre organisation obtient ces données, vous pouvez utiliser les attributs du client, une fonctionnalité d’Adobe Experience Cloud Platform. Cette fonctionnalité permet un contrôle total de l’organisation des données par attributs et ne se limite pas uniquement à la démographie ou aux intérêts.

Pour plus d’informations, voir l’aide sur les attributs du client.

## Géolinguistique

Le rapport Géolinguistique montre le trafic sur le site en fonction des paramètres linguistiques du navigateur du visiteur.

Pour créer un rapport linguistique :

1. Dans le menu Composants, recherchez la dimension **Langue** et faites-la glisser sur la grande zone de tableau à structure libre « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

Pour plus d’informations, voir la dimension [Langue](/help/components/c-variables/dimensionslist/reports-languages.md) dans le guide d’utilisation des composants.

## Géolocalisation

Le rapport Géolocalisation offre une analyse du panier à l’échelle mondiale, ventilant les données par pays.

Pour créer un rapport de géolocalisation :

1. Cliquez sur l’icône Visualisations à gauche, puis faites glisser la visualisation de carte sur l’espace de travail situé au-dessus du tableau à structure libre vide.
2. Cliquez sur l’icône Composants à gauche, puis faites glisser la mesure **Visiteurs uniques** dans l’espace « Ajouter une mesure ».
3. Cliquez sur Créer.

Si vous souhaitez obtenir le tableau en plus de la carte :

1. Dans le menu Composants, recherchez la dimension **Pays** et faites-la glisser sur la grande zone de tableau à structure libre « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

Pour plus d’informations, voir la dimension [Géosegmentation](/help/components/c-variables/dimensionslist/reports-geosegmentation.md) dans le guide d’utilisation des composants.

## Comportement - Visites nouvelles ou renouvelées

Le rapport Visites nouvelles ou renouvelées offre une vue simplifiée des premières sessions (nouvelles visites) et des sessions suivantes (visites renouvelées).

Pour créer un rapport Visites nouvelles ou renouvelées :

1. Dans le menu Composants, recherchez le segment **Premières visites** et faites-le glisser sur la grande zone de tableau à structure libre « Déposer une dimension ici ». Notez que **Premières visites** est un segment, alors que Workspace utilise généralement des dimensions pour représenter des lignes.
2. Recherchez le segment **Visites renouvelées** et faites-le glisser au-dessus de l’en-tête de la ligne Segments. Le segment est ainsi ajouté sous forme de dimension en dessous de Premières visites, ce qui facilite la comparaison.
3. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

Si vous souhaitez aussi obtenir un graphique linéaire :

1. Cliquez sur l’icône Visualisations à gauche, puis faites glisser la visualisation de ligne sur l’espace de travail situé au-dessus du tableau à structure libre.
2. Utilisez les touches ctrl+clic (Windows) ou cmd+clic (Mac) sur chaque ligne du tableau à structure libre pour les mettre en surbrillance. Cela permet aux deux tendances d’apparaître dans la visualisation de ligne.
3. Cliquez sur le petit point rond coloré dans le coin supérieur gauche de la visualisation de ligne, puis cochez la case « Verrouiller la sélection ».

## Comportement - Fréquence et récence

Le rapport Fréquence et récence est à peu près équivalent à la dimension **Nombre de visites** dans Analysis Workspace.

1. Dans le menu Composants, recherchez la dimension **Nombre de visites** et faites-la glisser sur la grande zone de tableau à structure libre « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

Pour plus d’informations, voir la dimension [Nombre de visites](/help/components/c-variables/dimensionslist/reports-visitor-number.md) dans le guide d’utilisation des composants.

## Comportement - Engagement

Le rapport Engagement est à peu près équivalent à la dimension **Durée de la visite - Valeur cumulée**.

1. Dans le menu Composants, recherchez la dimension **Durée de la visite - Valeur cumulée** et faites-la glisser sur la grande zone de tableau à structure libre « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

Pour plus d’informations, voir la dimension [Durée de la visite](/help/components/c-variables/dimensionslist/reports-time-spent-per-visit.md) dans le guide d’utilisation des composants.

## Technologie - Navigateur et système d’exploitation

Plusieurs dimensions principales sont disponibles dans le rapport Navigateur et système d’exploitation.

* La dimension principale **Navigateur** est aussi disponible comme dimension dans Analysis Workspace.
* La dimension principale **Système d’exploitation** est aussi disponible comme dimension dans Analysis Workspace.
* La dimension principale **Résolution d’écran** est disponible dans Analysis Workspace comme dimension **Résolution d’écran**.
* La dimension principale **Couleurs d’écran** est disponible dans Analysis Workspace comme dimension **Codage des couleurs**.
* La dimension principale **Version Flash** n’est pas disponible dans Adobe Analytics, mais ces données peuvent être collectées par une eVar, si nécessaire.

1. Dans le menu Composants, recherchez la dimension de votre choix affichée ci-dessus et faites-la glisser sur la grande zone de tableau à structure libre intitulée « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

Pour plus d’informations sur leurs dimensions respectives, voir les pages suivantes du guide d’utilisation des composants :

* [Navigateur](/help/components/c-variables/dimensionslist/reports-browsers.md)
* [Système d’exploitation](/help/components/c-variables/dimensionslist/reports-operating-system.md)
* [Résolution de l’écran](/help/components/c-variables/dimensionslist/reports-technology.md)
* [Codage des couleurs](/help/components/c-variables/dimensionslist/reports-color-depth.md)

## Technologie - Réseau

Le rapport Réseau est à peu près équivalent à la dimension **Domaine**.

1. Dans le menu Composants, recherchez la dimension **Domaine** et faites-la glisser sur la grande zone de tableau à structure libre « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

Pour plus d’informations, voir la dimension [Domaine](/help/components/c-variables/dimensionslist/reports-domains.md) dans le guide d’utilisation des composants.

## Mobile - Présentation

Le rapport Présentation mobile est à peu près équivalent à la dimension **Type d’appareil mobile**. Notez que la valeur « Autre » équivaut au trafic du bureau.

1. Dans le menu Composants, recherchez la dimension **Type d’appareil mobile** et faites-la glisser sur la grande zone de tableau à structure libre « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

Pour plus d’informations, voir la dimension [Type d’appareil mobile](/help/components/c-variables/dimensionslist/reports-device-types.md) dans le guide d’utilisation des composants.

## Mobile - Appareils

Le rapport Appareils mobiles est à peu près équivalent à la dimension **Appareil mobile**.

1. Dans le menu Composants, recherchez la dimension **Appareil mobile** et faites-la glisser sur la grande zone de tableau à structure libre « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

Pour plus d’informations, voir la dimension [Appareil mobile](/help/components/c-variables/dimensionslist/reports-devices.md) dans le guide d’utilisation des composants.

## Rapports personnalisés

Les rapports personnalisés sont définis selon chaque mise en œuvre. Faites appel à l’administrateur Analytics et/ou au consultant en mise en œuvre pour interpréter ces rapports. En règle générale, chaque organisation possède un [document de conception de solution](/help/implement/prepare/solution-design.md) pour effectuer un suivi des valeurs de variable personnalisée et de leur mode de remplissage.

## Évaluation

Les rapports d’évaluation permettent de comparer des facettes de vos données aux moyennes du secteur. Actuellement, Adobe ne partage aucune donnée d’évaluation avec ses clients.

## Flux utilisateurs

Le rapport de flux est disponible sur les deux plateformes. Pour créer un rapport de flux :

1. Cliquez sur l’icône Visualisations à gauche, puis faites glisser une visualisation de flux sur l’espace de travail situé au-dessus du tableau à structure libre.
2. Recherchez la dimension **Pages**, puis cliquez sur l’icône en forme de flèche pour afficher les valeurs de page. Les valeurs de dimension sont en jaune.
3. Recherchez la valeur de page de votre choix et faites-la glisser sur l’espace « Dimension ou élément » au centre.
4. Ce rapport de flux est interactif. Cliquez sur l’une des valeurs pour étendre les flux aux pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.
