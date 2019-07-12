---
title: Rapports d'acquisition dans Adobe Analytics
description: Découvrez comment créer des rapports basés sur l'acquisition à l'aide d'Analysis Workspace.
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# Rapports d&#39;acquisition

Les rapports d&#39;acquisition indiquent comment vous obtenez des visiteurs sur votre site.

In Adobe Analytics, these reports are known as **Marketing Channels**. Ils nécessitent une configuration initiale de base, mais permettent une vue bien plus personnalisée des canaux.

> [!IMPORTANT]
>
> Configurez les règles de traitement des canaux marketing pour utiliser ces rapports. See [Getting Started with Marketing Channels](../../../components/c-marketing-channels/c-getting-started-mchannel.md) for information on how to best configure Marketing Channels in your organization.

Cette page suppose que l&#39;utilisateur maîtrise de base l&#39;utilisation d&#39;Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Tout le trafic - Canaux

Affiche une vue agrégée de tous les canaux utilisés par les visiteurs pour atteindre votre site.

1. In the Components menu, locate the **Marketing Channel** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Tout le trafic - Treemaps

Affiche un treemap du trafic de canal. Ce rapport est semblable à Tous les trafics - Canaux, mais s&#39;affiche différemment.

1. Cliquez sur l&#39;icône Visualisations à gauche, puis faites glisser la visualisation Treemap sur l&#39;espace de travail au-dessus du tableau à structure libre vide.
2. Click the Components icon on the left, then drag the **Marketing Channel** dimension onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.
4. Notez que d&#39;autres mesures créent des cademap supplémentaires. Si un seul treemap est souhaité :
   1. Cliquez sur la cellule supérieure de la mesure souhaitée pour représenter le treemap.
   2. Maj + clic sur la dernière cellule de la même colonne de mesure pour mettre la colonne en surbrillance. S&#39;il est correctement effectué, un treemap est présent dans la visualisation.
   3. Cliquez sur le point coloré dans le coin supérieur droit de la visualisation treemap, puis cochez la case Verrouiller la sélection.

Les fichiers Treemaps peuvent être appliqués à n&#39;importe quelle dimension, et pas seulement aux canaux marketing.

## Tout trafic - Source/Moyen

Les rapports source et moyenne indiquent les domaines qui ont généré du trafic vers votre site.

* The **Source** primary dimension is available in Analysis Workspace as the **Referring Domain** dimension.
* The **Medium** primary dimension is available in Analysis Workspace as the  **Referrer Type** dimension.
* The **Keyword** primary dimension is available in Analysis Workspace as the **Search Keyword** dimension.

1. Dans le menu Composants, localisez la dimension souhaitée ci-dessus et faites-la glisser sur la grande zone de tableau à structure libre intitulée « Déposer une dimension ici ».
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Pour plus d&#39;informations sur la dimension correspondante, consultez les pages suivantes du Guide de l&#39;utilisateur des composants :

* [Domaine référent](../../../components/c-variables/dimensionslist/reports-referring-domains.md)
* [Type de référent](../../../components/c-variables/dimensionslist/reports-ref-types.md)
* [Mot-clé de recherche](../../../components/c-variables/dimensionslist/reports-search-keywords.md)

## Tout trafic - Références

* The **Source** primary dimension is available in Analysis Workspace as the **Referring Domain** dimension.
* The **Landing Page** primary dimension is available in Analysis Workspace as the **Entry Page** dimension.

1. In the components menu, locate the **Referring Domain** or **Entry Page** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Referring Domain](../../../components/c-variables/dimensionslist/reports-referring-domains.md) dimension in the Components user guide for more information.

## Rapports Google Publicités et rapports de console de recherche

Adobe utilise une fonctionnalité de l&#39;Espace de travail d&#39;analyse nommée Advertizing Analytics pour publier des données de publicité et de recherche depuis plusieurs plateformes, y compris Google.

La fonction d&#39;analyse de publicité nécessite une configuration pour renvoyer des données. See [Advertising Analytics Help](../../../integrate/c-advertising-analytics/overview.md) for details on how to enable these additional dimensions in Analysis Workspace.

## Rapports sur les réseaux sociaux

Les rapports Social fournissent des informations similaires comme le rapport Comportement respectif, sauf dans le contexte des réseaux sociaux. Ces données sont disponibles dans Analysis Workspace en combinant une dimension avec un segment.

Parfois, les visiteurs atteignent votre site par le biais de plusieurs canaux au cours de la même session. Par exemple, un visiteur clique sur une page de réseaux sociaux, puis quelques minutes plus tard, un moteur de recherche visite votre site. Dans ce cas, les domaines non sociaux peuvent apparaître dans ce rapport. Si vous souhaitez exclure les domaines non sociaux, triez le rapport par visites ou créez une copie du segment pour qu&#39;elle soit basée sur les accès plutôt que sur les visites. See [Segmentation Containers](../../../components/c-segmentation/seg-overview.md) in the Components user guide for more information.

### Social - Références réseau

Ce rapport indique quels domaines réseau sociaux ont conduit le trafic vers votre site. This data is available in Analysis Workspace using the **Referring Domain** dimension and **Visits from Social Sites** segment.

1. In the Components menu, locate the **Referring Domain** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. In the Components menu, locate the **Visits from Social Sites** segment and drag in onto the small area just above the freeform table labeled &#39;Drop a segment here&#39;.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

### Social - Pages d&#39;entrée

Le rapport Pages d&#39;entrée indique les pages sur lesquelles les visiteurs sont arrivés après avoir cliqué sur un lien via un réseau social. This data is available in Analysis Workspace using the **Entry Page** dimension and **Visits from Social Sites** segment.

1. In the Components menu, locate the **Entry Page** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. In the Components menu, locate the **Visits from Social Sites** segment and drag in onto the small area just above the freeform table labeled &#39;Drop a segment here&#39;.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

### Social - Conversions

Le rapport Conversions montre les données de commerce électronique dans le contexte des réseaux sociaux. Une mise en œuvre supplémentaire est nécessaire pour utiliser ces rapports sur les deux plateformes ; Adobe conseille de travailler avec un conseiller en implémentation pour vérifier que ces données sont correctement configurées pour Analysis Workspace.

### Social - Modules externes

Ce rapport montre comment les visiteurs interagissent avec les modules externes de médias sociaux intégrés sur votre site. Une mise en œuvre supplémentaire est requise pour l&#39;utilisation dans Analysis Workspace. Adobe conseille de travailler avec un conseiller en implémentation pour veiller à ce que ces données soient collectées avec précision.

### Social - Flux des utilisateurs

Le rapport Flux utilisateurs affiche les données de cheminement dans le contexte des visiteurs qui sont arrivés sur un réseau social.

1. Cliquez sur l&#39;icône de visualisation à gauche, puis faites glisser une visualisation Flux sur l&#39;espace de travail au-dessus du tableau à structure libre.
2. Click the Components icon on the left, then drag the **Visits from Social Sites** segment onto the small area just above the flow visualization labeled &#39;Drop a Segment here&#39;.
3. Locate the **Pages** dimension, then click the Arrow icon to reveal page values. Les valeurs de dimension sont colorées jaune.
4. Localisez la valeur de page souhaitée pour commencer avec, puis faites-la glisser dans l&#39;espace intitulé Dimension ou élément au centre.
5. Ce rapport de flux est interactif. Cliquez sur l&#39;une des valeurs pour développer les flux vers les pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire les colonnes. Différentes dimensions peuvent également être utilisées dans le même rapport de flux.

## Campagnes - Tous

The campaigns report is available in Analysis Workspace using the **Tracking Code** dimension. Notez que l&#39;utilisation de la dimension Code de suivi requiert une implémentation supplémentaire pour collecter des données.

Il est possible de collecter des paramètres UTM dans Adobe Analytics à l&#39;aide de variables personnalisées (evars). Adobe conseille de travailler avec un conseiller en implémentation pour garantir la collecte exacte des valeurs de code de suivi dans Adobe Analytics.

1. In the Components menu, locate the **Tracking Code** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Campagnes - Mots-clés payés

Le rapport Mots-clés payés indique comment chaque mot-clé se produit après que le visiteur a cliqué sur un lien de recherche payante à partir d&#39;un moteur de recherche. The **Search Keywords - Paid** dimension is available in Analysis Workspace, but requires a one-time setup of paid search detection to collect data. See [Paid Search Detection](../../../admin/admin/paid-search-detection/paid-search-detection.md) in the Admin user guide for setup details.

1. In the Components menu, locate the **Search Keyword - Paid** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Campagnes - Mots-clés organiques

Le rapport Mots-clés organiques indique comment chaque mot-clé se produit après que le visiteur a cliqué sur un lien de recherche organique à partir d&#39;un moteur de recherche. The **Search Keywords - Natural** dimension is available in Analysis Workspace. Notez que si la détection de recherche payée n&#39;est pas configurée, cette dimension collecte les mots-clés payants et naturels.

1. In the Components menu, locate the **Search Keyword - Natural** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Analyse des coûts

Ce rapport montre les données de performance des visites, des coûts et des recettes pour vos canaux marketing payants. Adobe fournit un produit dédié qui fournit des informations appelées Adobe Advertizing Cloud. Si votre organisation souhaite utiliser ce produit, contactez le gestionnaire de compte de votre entreprise.
