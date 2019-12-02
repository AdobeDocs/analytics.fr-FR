---
title: Rapports d’audience dans Adobe Analytics
description: Découvrez comment créer des rapports basés sur l’audience à l’aide d’Analysis Workspace.
translation-type: tm+mt
source-git-commit: 6217430bf0ae9c0f9c6426e4bb2a8101257068e7

---


# Rapports Audience

Les rapports Audience affichent des informations sur les types de personnes qui visitent votre site.

Cette page suppose que l’utilisateur a une connaissance de base de l’utilisation d’Analysis Workspace. Voir [Création d’un rapport de base dans Analysis Workspace pour les utilisateurs](create-report.md) de Google Analytics si vous ne connaissez pas encore l’outil dans Adobe Analytics.

## Utilisateurs actifs

Les utilisateurs actifs affichent le nombre cumulé d’utilisateurs sur votre site au cours des 1, 7, 14 ou 28 jours précédents. Bien qu’Adobe ne dispose pas du calcul exact utilisé dans Google Analytics, vous pouvez utiliser la mesure Visiteurs uniques pour afficher un nombre dédupliqué d’utilisateurs sur votre site en fonction de la période sélectionnée.

Pour obtenir un graphique linéaire de visiteurs uniques :

1. Cliquez sur l’icône Visualisations sur la gauche, puis faites glisser la visualisation Ligne sur l’espace de travail au-dessus du tableau à structure libre vide.
2. Cliquez sur l’icône Composants sur la gauche, puis faites glisser la mesure Visiteurs **** uniques dans le plus petit espace intitulé "Déposer une mesure ici".
3. Si vous souhaitez une granularité différente, faites glisser la plage de dates souhaitée (par exemple, **Jour**, **Semaine**, **Mois**, etc.). au-dessus de l’en-tête de dimension de date existant.

Voir Visiteurs [](/help/components/c-variables/c-metrics/metrics-unique-visitors.md) uniques dans le guide de l’utilisateur Composants pour en savoir plus sur la manière dont Adobe calcule les visiteurs uniques.

## Valeur de durée de vie

La valeur de durée de vie est une fonctionnalité qui nécessite une implémentation spécialisée supplémentaire sur les deux plates-formes. Adobe recommande de travailler avec un consultant en implémentation pour obtenir ces données.

## Analyse des cohortes

L’analyse des cohortes montre la fréquence à laquelle les mêmes utilisateurs reviennent sur votre site.

Pour créer un tableau de cohortes :

1. Cliquez sur l’icône de visualisation à gauche, puis faites glisser la visualisation Tableau de cohortes sur l’espace de travail.
2. Cliquez sur l’icône Composants sur la gauche, puis faites glisser la mesure **Visites** sur les critères d’inclusion et de retour.
3. Cliquez sur Créer.

Voir Analyse des [cohortes](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) dans le guide de l’utilisateur d’Analysis Workspace pour en savoir plus sur les personnalisations supplémentaires de la visualisation des cohortes.

## Audiences

Le rapport Audiences dans Google Analytics nécessite la configuration des audiences. Les audiences nécessitent également une configuration dans Adobe via Adobe Audience Manager. Pour plus d’informations, consultez le guide de l’utilisateur d’Adobe Audience Manager.

## Explorateur d’utilisateurs

Le rapport Explorateur d’utilisateurs permet à un analyste d’afficher des visites individuelles au moyen d’identifiants anonymes. Adobe n’utilise pas les identifiants d’arrière-plan en dehors des flux de données, qui sont des exportations brutes de données au niveau de l’accès.

* Si ces données sont souhaitées dans Analysis Workspace, il est possible de collaborer avec un consultant en implémentation pour transmettre la valeur du cookie d’identifiant unique anonyme dans une eVar. Notez que cela ne fonctionne qu’avec des implémentations plus petites comprenant moins d’un million de visiteurs uniques par mois.
* Si ces données sont souhaitées dans les flux de données, les colonnes concaténées `visid_high` et `visid_low` constituent la méthode la plus courante pour identifier les visiteurs uniques. Pour en savoir plus sur les flux [de](/help/export/analytics-data-feed/data-feed-overview.md) données, consultez le guide de l’utilisateur Exporter.

## Rapports Démographie et Intérêts

Les données démographiques et d’intérêt fournissent des informations sur l’âge, le sexe et les intérêts des utilisateurs du site. Ces données sont collectées par Google grâce à leurs capacités de suivi inter-sites.

Les données démographiques et d’intérêt ne sont pas automatiquement collectées par Adobe. Toutefois, si votre entreprise obtient ces données, vous pouvez utiliser les attributs du client, une fonctionnalité de la plateforme Adobe Experience Cloud. Il permet un contrôle total de l'organisation des données par attributs, et ne se limite pas uniquement aux données démographiques ou aux intérêts.

Pour plus d’informations, voir l’aide Attributs du client.

## Géo - Langue

Le rapport Langue géographique montre le trafic du site par paramètre de langue dans le navigateur du visiteur.

Pour créer un rapport de langue :

1. Dans le menu Composants, recherchez la dimension **Langage** et faites-la glisser sur la grande zone de tableau à structure libre intitulée "Déposer une dimension ici".
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

Pour plus d’informations, voir la dimension [Langue](/help/components/c-variables/dimensionslist/reports-languages.md) dans le guide de l’utilisateur Composants.

## Géo - Emplacement

Le rapport de géolocalisation donne une vue cartographique mondiale, ventilant les données par pays.

Pour créer un rapport de géolocalisation :

1. Cliquez sur l’icône Visualisations sur la gauche, puis faites glisser la visualisation Carte sur l’espace de travail au-dessus du tableau à structure libre vide.
2. Cliquez sur l’icône Composants sur la gauche, puis faites glisser la mesure Visiteurs **** uniques dans l’espace intitulé "Ajouter une mesure".
3. Cliquez sur Créer.

Si le tableau est également souhaité en plus de la carte :

1. Dans le menu Composants, recherchez la dimension **Pays** et faites-la glisser sur la grande zone de tableau à structure libre intitulée "Déposer une dimension ici".
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

Pour plus d’informations, voir Dimensions [de géosegmentation](/help/components/c-variables/dimensionslist/reports-geosegmentation.md) dans le guide de l’utilisateur Composants.

## Comportement - Nouveau ou Retour

Le rapport Nouveau vs. retour offre une vue simplifiée des premières sessions (nouvelles visites) par rapport aux sessions suivantes (visites de retour).

Pour créer un rapport sur les visites nouvelles ou récurrentes :

1. Dans le menu des composants, recherchez le segment **Premières visites** et faites-le glisser sur la grande zone de tableau à structure libre intitulée "Déposer une dimension ici". Notez que les **premières visites** sont un segment, tandis que Workspace utilise généralement des dimensions pour représenter des lignes.
2. Recherchez le segment Visites **de retour** et faites-le glisser au-dessus de l’en-tête de ligne Segments. Ceci ajoute le segment sous la forme d’une dimension sous Premières visites, ce qui facilite la comparaison.
3. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

Si un graphique linéaire est également souhaité :

1. Cliquez sur l’icône des visualisations sur la gauche, puis faites glisser une visualisation Ligne sur l’espace de travail au-dessus du tableau à structure libre.
2. Utilisez les touches Ctrl+clic (Windows) ou cmd+clic (Mac) sur chaque ligne du tableau à structure libre pour les mettre en surbrillance. Cela permet aux deux tendances d’apparaître dans la visualisation en ligne.
3. Cliquez sur le petit point rond dans le coin supérieur gauche de la visualisation des lignes, puis cochez la case "Verrouiller la sélection".

## Comportement - Fréquence et récence

Le rapport Fréquence et récence est approximativement égal à la dimension Nombre **de** visites dans Analysis Workspace.

1. Dans le menu des composants, recherchez la dimension Nombre **de** visites et faites-la glisser sur la grande zone de tableau à structure libre intitulée "Déposez une dimension ici".
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

Pour plus d’informations, voir la dimension Nombre [de](/help/components/c-variables/dimensionslist/reports-visitor-number.md) visites dans le guide de l’utilisateur Composants.

## Comportement - Engagement

Le rapport d’engagement est approximativement égal à la dimension **Durée de la visite - Regroupement** .

1. Dans le menu des composants, recherchez la dimension **Durée de la visite - Regroupement** et faites-la glisser sur la grande zone de tableau à structure libre intitulée "Déposer une dimension ici".
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

Pour plus d’informations, voir la dimension [Durée de la visite](/help/components/c-variables/dimensionslist/reports-time-spent-per-visit.md) dans le guide de l’utilisateur Composants.

## Technologie - Navigateur et système d’exploitation

Plusieurs dimensions principales sont disponibles dans le rapport Navigateur et système d’exploitation.

* La dimension principale **Navigateur** est également disponible en tant que dimension dans Analysis Workspace.
* La dimension principale du système **d’exploitation** est également disponible dans Analysis Workspace en tant que dimension.
* La dimension principale Résolution **** d’écran est disponible dans Analysis Workspace en tant que dimension Résolution **de l’** écran.
* La dimension principale Couleurs **d’** écran est disponible dans Analysis Workspace sous forme de dimension Profondeur **de** couleur.
* La dimension principale Version **** Flash n’est pas disponible dans Adobe Analytics, mais ces données peuvent être collectées par une eVar si nécessaire.

1. Dans le menu des composants, recherchez la dimension souhaitée mentionnée ci-dessus et faites-la glisser sur la grande zone de tableau à structure libre intitulée "Déposez une dimension ici".
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

Pour plus d’informations sur leurs dimensions respectives, consultez les pages suivantes du guide de l’utilisateur Composants :

* [Navigateur](/help/components/c-variables/dimensionslist/reports-browsers.md)
* [Système d’exploitation](/help/components/c-variables/dimensionslist/reports-operating-system.md)
* [Résolution de l’écran](/help/components/c-variables/dimensionslist/reports-technology.md)
* [Profondeur de couleur](/help/components/c-variables/dimensionslist/reports-color-depth.md)

## Technologie - Réseau

Le rapport réseau est approximativement égal à la dimension **Domaine** .

1. Dans le menu des composants, recherchez la dimension **Domaine** et faites-la glisser sur la grande zone de tableau à structure libre intitulée "Déposez une dimension ici".
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

Pour plus d’informations, voir la dimension [Domaine](/help/components/c-variables/dimensionslist/reports-domains.md) dans le guide de l’utilisateur Composants.

## Mobile - Présentation

Le rapport d’aperçu des dispositifs portables est approximativement égal à la dimension Type **de dispositifs** mobiles. Notez que la valeur "Autre" équivaut au trafic sur le bureau.

1. Dans le menu des composants, recherchez la dimension Type **de périphérique** mobile et faites-la glisser sur la grande zone de tableau à structure libre intitulée "Déposez une dimension ici".
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

Pour plus d’informations, voir la dimension Type [de périphérique](/help/components/c-variables/dimensionslist/reports-device-types.md) mobile dans le guide de l’utilisateur Composants.

## Mobile - Périphériques

Le rapport Périphériques mobiles est approximativement égal à la dimension Périphérique **** mobile.

1. Dans le menu des composants, recherchez la dimension Périphérique **** mobile et faites-la glisser sur la grande zone de tableau à structure libre intitulée "Déposez une dimension ici".
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

Pour plus d’informations, voir la dimension Périphérique [](/help/components/c-variables/dimensionslist/reports-devices.md) mobile dans le guide de l’utilisateur Composants.

## Personnalisé

Les rapports personnalisés sont définis par implémentation. Contactez l’administrateur Analytics et/ou le consultant en implémentation de votre entreprise pour interpréter ces rapports. En règle générale, une entreprise gère un document [de conception de](/help/implement/prepare/solution-design.md) solution pour suivre les valeurs de variable personnalisée et leur mode de remplissage.

## Évaluation

Les rapports de test vous permettent de comparer les facettes de vos données aux moyennes du secteur. Adobe ne partage actuellement aucune donnée d’analyse comparative entre ses clients.

## Flux utilisateurs

Le rapport de flux est disponible sur les deux plates-formes. Pour créer un rapport de flux :

1. Cliquez sur l’icône de visualisation à gauche, puis faites glisser une visualisation Flux sur l’espace de travail au-dessus du tableau à structure libre.
2. Recherchez la dimension **Pages** , puis cliquez sur l’icône de flèche pour afficher les valeurs de page. Les valeurs de dimension sont colorées en jaune.
3. Localisez la valeur de page de votre choix et faites-la glisser dans l’espace "Dimension ou élément" au centre.
4. Ce rapport de flux est interactif. Cliquez sur l’une des valeurs pour étendre les flux aux pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.
