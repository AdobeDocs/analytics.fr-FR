---
title: Meilleures pratiques en matière de Rapports et dépannage
description: Meilleures pratiques et conseils de dépannage lors de la création de rapports.
keywords: best practices;failure;timeout;troubleshooting;slow
translation-type: tm+mt
source-git-commit: 1968162d856b6a74bc61f22f2e5a6b1599d04c79
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 58%

---


# Meilleures pratiques en matière de Rapports et dépannage

*Cette page d’aide fait référence aux bonnes pratiques des rapports et analyses. Pour Analyse Workspace, voir[Optimisation des performances](../analysis-workspace/workspace-faq/optimizing-performance.md)de Analyse Workspace. Pour l’entrepôt de données, voir les bonnes pratiques[de l’entrepôt de](/help/export/data-warehouse/data-warehouse-bp.md)données.*

Adobe Analytics offre une interface de création de rapports souple qui permet de générer un large éventail de rapports complexes. Bien que la plupart des rapports soient générés très rapidement, vous pouvez rencontrer des rapports qui expirent ou ne se génèrent pas. Cette page explique les facteurs qui ont un impact sur la vitesse de génération des rapports. La compréhension de ces informations peut vous aider à structurer les rapports afin qu’ils soient plus susceptibles de générer avec succès.

## Délais d’expiration des rapports et file d’attente des demandes

* **Délais d&#39;expiration**: Un rapport unique est fractionné en plusieurs requêtes (une par ventilation) et chaque requête est sujette à un dépassement de délai individuel. Des délais d’expiration plus longs sont accordés aux rapports planifiés. Ainsi, ces derniers ont plus de chance de succès que les rapports générés directement dans une interface utilisateur.
* **File d’attente des suites de rapports**: Chaque suite de rapports conserve une file d’attente distincte de demandes. Si de nombreux rapports sont demandés simultanément, même en provenance d’utilisateurs distincts, un faible nombre de rapports sont générés simultanément. Lorsque les rapports se terminent, les rapports restants sont générés dans l’ordre dans lequel ils sont reçus. En conséquence, si un grand nombre de rapports complexes se trouvent déjà dans la file d’attente des suites de rapports, un rapport qui est habituellement créé rapidement peut expirer.

## Facteurs qui affectent la vitesse des rapports

Les facteurs suivants contribuent à rallonger le délai de génération des rapports. L’augmentation de l’un de ces facteurs n’a généralement pas d’incidence sur les performances, mais elle peut retarder d’autres rapports dans la file d’attente de la suite de rapports et provoquer l’expiration d’un rapport ultérieur.

* **Période** du rapport : Le facteur le plus important qui affecte le temps de génération des rapports est le nombre de mois demandé. La réduction du nombre de mois de trois à un diminue significativement le délai de génération mais la réduction de la période d’un mois à une semaine n’a pas un impact important sur le délai de génération.
* **Nombre de mesures**: Alors que le nombre de mesures augmente, le délai d’exécution du rapport augmente. La suppression des mesures améliore souvent le délai de génération des rapports.
* **Nombre de ventilations**: Dans un rapport, chaque ventilation représente une demande distincte. Alors que des demandes individuelles peuvent se terminer rapidement, l’exécution de milliers de ventilations dans un seul rapport peut ralentir de manière significative le délai de génération des rapports et affecter la file d’attente de la suite de rapports.
* **Complexité** des segments : Les segments qui prennent en compte de nombreuses dimensions ou qui comportent de nombreuses règles (24+) augmentent l’impact du traitement et la durée de génération des rapports.
* **Nombre de valeurs** uniques : Les rapports qui contiennent des centaines de milliers de valeurs uniques sont générés plus lentement que les rapports qui contiennent moins de valeurs uniques, même si le segment ou le filtre réduit le nombre de valeurs qui apparaissent finalement dans un rapport. Par exemple, un rapport qui affiche des termes de recherche est généré habituellement plus lentement que les autres rapports, même si un filtre est appliqué afin d’afficher uniquement les termes de recherche qui contiennent une valeur spécifique.

## Autres options de rapports

Les recommandations suivantes contribuent à accroître la fiabilité de la diffusion de rapports :

* Utilisez Data Warehouse pour demander des rapports qui contiennent de nombreuses ventilations ou mesures. Data Warehouse est conçu pour générer ces types de rapports.
* Planifiez les rapports pour qu’ils s’exécutent aux heures creuses. Cela augmente la probabilité d’un retour de rapport puisque la file d’attente des demandes d’une suite de rapports sera vraisemblablement vide aux heures creuses.
* Vous pouvez utiliser le Report Builder pour ventiler les rapports en périodes et demandes plus petites qui contiennent moins de mesures. Vous pouvez alors utiliser une fonctionnalité Excel native pour fusionner les données provenant de différentes demandes dans un seul rapport.
