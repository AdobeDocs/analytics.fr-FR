---
title: Rapports d'audience dans Adobe Analytics
description: Découvrez comment créer des rapports basés sur l'audience à l'aide d'Analysis Workspace.
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# Rapports d&#39;audience

Les rapports d&#39;audience affichent des informations sur les types de personnes qui visitent votre site.

Cette page suppose que l&#39;utilisateur maîtrise de base l&#39;utilisation d&#39;Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Utilisateurs actifs

Les utilisateurs actifs affichent le nombre total d&#39;utilisateurs sur votre site au cours des 1, 7, 14 ou 28 derniers jours. Bien qu&#39;Adobe ne dispose pas du calcul exact utilisé dans Google Analytics, vous pouvez utiliser la mesure Visiteurs uniques pour afficher un nombre dédupliqué d&#39;utilisateurs sur votre site en fonction de la plage de dates sélectionnée.

Pour obtenir un graphique linéaire des visiteurs uniques :

1. Cliquez sur l&#39;icône Visualisations à gauche, puis faites glisser la visualisation Line sur l&#39;espace de travail au-dessus du tableau à structure libre vide.
2. Click the Components icon on the left, then drag the **Unique Visitors** metric into the smaller space labeled &#39;Drop a Metric here&#39;.
3. If different granularity is desired, drag the desired date range (e.g. **Day**, **Week**, **Month**, etc.) au-dessus de l&#39;en-tête de dimension de date existant.

See [Unique Visitors](../../../components/c-variables/c-metrics/metrics-unique-visitors.md) in the Components user guide for details on how Adobe calculates unique visitors.

## Valeur de durée de vie

La valeur de durée de vie est une fonctionnalité qui requiert une mise en œuvre spécialisée supplémentaire sur les deux plateformes. Adobe conseille de travailler avec un conseiller en implémentation pour obtenir ces données.

## Analyse des cohortes

L&#39;analyse des cohortes indique la fréquence à laquelle les mêmes utilisateurs reviennent sur votre site.

Pour créer un tableau de cohortes :

1. Cliquez sur l&#39;icône Visualisation à gauche, puis faites glisser la visualisation du tableau de cohortes sur l&#39;espace de travail.
2. Click the Components icon on the left, then drag the **Visits** metric onto both the Inclusion Criteria and Return Criteria.
3. Cliquez sur Créer.

See [Cohort Analysis](../../../analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) in the Analysis Workspace user guide for details on additional customizations to the cohort visualization.

## Audiences

Le rapport Audiences de Google Analytics requiert le paramètre - plus d&#39;audiences. Les audiences doivent également être configurées dans Adobe par le biais d&#39;Adobe Audience Manager. Pour plus d&#39;informations, consultez le Guide de l&#39;utilisateur d&#39;Adobe Audience Manager.

## Explorateur d&#39;utilisateur

Le rapport Explorateur d&#39;utilisateurs permet à un analyste d&#39;afficher les visites individuelles par le biais d&#39;identifiants anonymes. Adobe ne met pas en surface les identifiants Backend en dehors des flux de données, qui sont des exportations brutes de données brutes au niveau de l&#39;accès.

* Si ces données sont souhaitées dans Analysis Workspace, il est possible de travailler avec un conseiller en implémentation pour transmettre la valeur du cookie d&#39;identificateur unique anonyme à une evar. Notez que cela fonctionne uniquement avec les implémentations plus petites comprenant moins d&#39;un million de visiteurs uniques par mois.
* If this data is desired within data feeds, the concatenated columns `visid_high` and `visid_low` are the most common way to identify unique visitors. Learn more about [Data Feeds](../../../export/analytics-data-feed/c-getstarted/data-feed-overview.md) in the Export user guide.

## Rapports démographiques et d&#39;intérêts

Les données démographiques et d&#39;intérêt fournissent des informations sur l&#39;âge, le sexe et les intérêts des utilisateurs du site. Ces données sont collectées par Google par le biais de leurs capacités de suivi inter-sites.

Adobe ne collecte pas automatiquement les données démographiques et d&#39;intérêts. Toutefois, si votre organisation obtient ces données, vous pouvez utiliser Attributs du client, une fonctionnalité de la plate-forme Adobe Experience Cloud. Il permet un contrôle total sur l&#39;organisation des données par attributs et n&#39;est pas limité aux seules données démographiques ou intérêts.

Pour plus d&#39;informations, voir Aide sur les attributs du client.

## Géo - Langue

Le rapport de langue géographique indique le trafic du site par paramètre de langue dans le navigateur du visiteur.

Pour créer un rapport de langue :

1. In the Components menu, locate the **Language** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Language](../../../components/c-variables/dimensionslist/reports-languages.md) dimension in the Components user guide for more information.

## Géo - Emplacement

Le rapport de géolocalisation fournit une vue globale, en ventilant les données par pays.

Pour créer un rapport de géolocalisation :

1. Cliquez sur l&#39;icône Visualisations à gauche, puis faites glisser la visualisation de carte sur l&#39;espace de travail au-dessus du tableau à structure libre vide.
2. Click the Components icon on the left, then drag the **Unique Visitors** metric into the space labeled &#39;Add Metric&#39;.
3. Cliquez sur Créer.

Si le tableau est également souhaité en plus de la carte :

1. In the Components menu, locate the **Countries** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See [Geosegmentation](../../../components/c-variables/dimensionslist/reports-geosegmentation.md) dimensions in the Components user guide for more information.

## Comportement - Nouveau vs Retour

Le nouveau rapport et le rapport de retour donnent une vue simplifiée des premières sessions (nouvelles visites) par rapport aux sessions suivantes (visites de retour).

Pour créer un rapport sur les visites par rapport aux visites de retour :

1. In the components menu, locate the **First Time Visits** segment and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;. Note that **First Time Visits** is a segment, while Workspace typically uses dimensions to represent rows.
2. Locate the **Return Visits** segment and drag it on top of the Segments row header. Ceci ajoute le segment sous forme de dimension au-dessous des premières visites, ce qui permet une comparaison facile.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Si un graphique linéaire est également souhaité :

1. Cliquez sur l&#39;icône de visualisation à gauche, puis faites glisser une visualisation Ligne sur l&#39;espace de travail au-dessus du tableau à structure libre.
2. Utilisez ctrl + clic (Windows) ou cmd + clic (Mac) sur chaque ligne du tableau à structure libre pour les mettre en surbrillance. Cela permet aux deux tendances d&#39;apparaître dans la visualisation en ligne.
3. Cliquez sur le petit point coloré rond dans le coin supérieur gauche de la visualisation de ligne, puis cochez la case Verrouiller la sélection.

## Comportement - Fréquence et récence

The frequency &amp; recency report is approximately equal to the **Visit Number** dimension in Analysis Workspace.

1. In the components menu, locate the **Visit Number** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Visit Number](../../../components/c-variables/dimensionslist/reports-visitor-number.md) dimension in the Components user guide for more information.

## Comportement - Engagement

The engagement report is approximately equal to the **Time Spent per Visit - Bucketed** dimension.

1. In the components menu, locate the **Time Spent per Visit - Bucketed** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Time Spent per Visit](../../../components/c-variables/dimensionslist/reports-time-spent-per-visit.md) dimension in the Components user guide for more information.

## Technologie - Navigateur et OS

Plusieurs dimensions principales sont disponibles dans le rapport Navigateur et OS.

* The **Browser** primary dimension is also available in Analysis Workspace as a dimension.
* The **Operating System** primary dimension is also available in Analysis Workspace as a dimension.
* The **Screen Resolution** primary dimension is available in Analysis Workspace as the **Monitor Resolution** dimension.
* The **Screen Colors** primary dimension is available in Analysis Workspace as the **Color Depth** dimension.
* The **Flash Version** primary dimension is not available in Adobe Analytics, however this data can be collected by an eVar if wanted.

1. Dans le menu Composants, localisez la dimension souhaitée ci-dessus et faites-la glisser sur la grande zone de tableau à structure libre intitulée « Déposer une dimension ici ».
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Pour plus d&#39;informations sur la dimension correspondante, consultez les pages suivantes du Guide de l&#39;utilisateur des composants :

* [Navigateur](../../../components/c-variables/dimensionslist/reports-browsers.md)
* [Système d’exploitation](../../../components/c-variables/dimensionslist/reports-operating-system.md)
* [Résolution de l’écran](../../../components/c-variables/dimensionslist/reports-technology.md)
* [Profondeur de couleur](../../../components/c-variables/dimensionslist/reports-color-depth.md)

## Technologie - Réseau

The network report is approximately equal to the **Domain** dimension.

1. In the components menu, locate the **Domain** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Domain](../../../components/c-variables/dimensionslist/reports-domains.md) dimension in the Components user guide for more information.

## Mobile - Aperçu

The mobile overview report is approximately equal to the **Mobile Device Type** dimension. Notez que la valeur « Autre » équivaut au trafic de bureau.

1. In the components menu, locate the **Mobile Device Type** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Mobile Device Type](../../../components/c-variables/dimensionslist/reports-device-types.md) dimension in the Components user guide for more information.

## Mobile - Périphériques

The mobile devices report is approximately equal to the **Mobile Device** dimension.

1. In the components menu, locate the **Mobile Device** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Mobile Device](../../../components/c-variables/dimensionslist/reports-devices.md) dimension in the Components user guide for more information.

## Personnalisé

Les rapports personnalisés sont définis par implémentation. Consultez l&#39;administrateur Analytics et/ou le conseiller en implémentation de votre organisation pour interpréter ces rapports. Typically an organization maintains a [Solution Design Document](../../../implement/prepare/solution-design.md) to keep track of custom variable values and how they are populated.

## Évaluations

L&#39;évaluation des rapports vous permet de comparer les facettes de vos données aux moyennes du secteur. À l&#39;heure actuelle, Adobe ne partage pas les données d&#39;évaluation entre ses clients.

## Flux utilisateurs

Le rapport de flux est disponible sur les deux plateformes. Pour créer un rapport de flux :

1. Cliquez sur l&#39;icône de visualisation à gauche, puis faites glisser une visualisation Flux sur l&#39;espace de travail au-dessus du tableau à structure libre.
2. Locate the **Pages** dimension, then click the Arrow icon to reveal page values. Les valeurs de dimension sont colorées jaune.
3. Localisez la valeur de page souhaitée pour commencer avec, puis faites-la glisser dans l&#39;espace intitulé Dimension ou élément au centre.
4. Ce rapport de flux est interactif. Cliquez sur l&#39;une des valeurs pour développer les flux vers les pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire les colonnes. Différentes dimensions peuvent également être utilisées dans le même rapport de flux.
