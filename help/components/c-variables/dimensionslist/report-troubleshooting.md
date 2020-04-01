---
description: Adobe Analytics offre une interface de  souple qui vous permet de générer divers rapports complexes. Bien que la plupart des rapports soient générés très rapidement, il se peut que vous rencontriez des rapports qui expirent ou échouent à générer correctement. Pour éviter les échecs de génération de rapports, cette section explique de nombreux facteurs qui affectent la vitesse de génération des rapports. La compréhension de ces informations peut vous aider à structurer les rapports afin qu’ils soient plus susceptibles d’être générés avec succès.
keywords: best practices;failure;timeout;troubleshooting;slow
title: Bonnes pratiques et dépannage de la création de rapports
topic: Reports
uuid: d4eef0a3-1d26-4460-8a2b-962001c9f846
translation-type: tm+mt
source-git-commit: dca5bac72a2cf5f5ded5072e1867676392a7850e

---


# Bonnes pratiques et dépannage de la création de rapports

Adobe Analytics offre une interface de  souple qui vous permet de générer divers rapports complexes. Bien que la plupart des rapports soient générés très rapidement, il se peut que vous rencontriez des rapports qui expirent ou échouent à générer correctement. Pour éviter les échecs de génération de rapports, cette section explique de nombreux facteurs qui affectent la vitesse de génération des rapports. La compréhension de ces informations peut vous aider à structurer les rapports afin qu’ils soient plus susceptibles d’être générés avec succès.

>[!Note] :
>ces recommandations s’appliquent à Reports &amp; Analytics, à Ad Hoc Analysis et à Report Builder.
>Elles ne s’appliquent pas à Analysis Workspace, qui possède son propre ensemble de [bonnes pratiques](/help/analyze/analysis-workspace/workspace-faqs/optimizing-performance.md). Elles ne s’appliquent pas non plus aux [bonnes pratiques](https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse_bp.html) de Data Warehouse. Un ensemble supplémentaire de
>[bonnes pratiques](https://marketing.adobe.com/developer/en_US/get-started/best-practices/c-best-practices) est disponible dans l’API de création de rapports d’Adobe Analytics.

## Délais d’expiration des rapports et file d’attente des demandes {#section_A42AD7E487C749B7B879BAFA814FFEF9}

**Délais d’expiration**

Un rapport unique est divisé en plusieurs requêtes (une par ventilation) et chaque requête est soumise à un délai d’expiration individuel. Les rapports planifiés se voient accorder des délais d’expiration plus longs et sont plus susceptibles de réussir que les rapports générés directement dans une interface utilisateur.

**File d&#39;attente de Report Suite**

Chaque suite de rapports conserve une file d’attente de requêtes distincte. Si de nombreux rapports sont demandés simultanément, même par des utilisateurs distincts, un petit nombre de rapports sont générés simultanément. Une fois les rapports terminés, les rapports restants sont générés dans l’ordre dans lequel ils ont été reçus. Par conséquent, si un grand nombre de rapports complexes se trouvent déjà dans la file d’attente de la suite de rapports, un rapport généré généralement rapidement peut expirer.

## Facteurs qui affectent la vitesse des rapports  {#section_6BA937EB6CEC4CBCB71FAAD32F031DC2}

Les facteurs suivants contribuent à allonger les durées de génération des rapports. L’augmentation de l’un de ces facteurs peut ne pas générer de délai d’expiration pour ce rapport, mais peut retarder d’autres rapports dans la file d’attente de la suite de rapports et entraîner l’expiration d’un rapport ultérieur.

**Période du rapport**

Le facteur le plus important qui affecte le temps de génération du rapport est le nombre de mois demandés. La réduction du nombre de mois de trois à un réduit significativement le temps de génération, mais la réduction de la période d’un mois à une semaine n’a pas d’impact important sur le temps de génération des rapports.

**Nombre de mesures**

À mesure que le nombre de mesures augmente, le temps d’exécution du rapport augmente. La suppression des mesures améliore souvent le temps de génération des rapports.

**Nombre de ventilations**

Dans un rapport, chaque ventilation représente une requête distincte. Alors que des demandes individuelles peuvent se terminer rapidement, l’exécution de milliers de ventilations dans un seul rapport peut ralentir de manière significative le délai de génération des rapports et affecter la file d’attente de la suite de rapports.

**Complexité des segments**

Les segments qui prennent en compte de nombreuses dimensions ou qui comportent de nombreuses règles (24+) augmentent l’impact du traitement et le temps de génération du rapport.

**Nombre de valeurs uniques**

Les rapports qui contiennent des centaines de milliers de valeurs uniques sont générés plus lentement que les rapports qui contiennent moins de valeurs uniques, même si le segment ou le filtre réduit le nombre de valeurs qui apparaissent finalement dans un rapport. Par exemple, un rapport qui affiche des termes de recherche est généralement généré plus lentement que les autres rapports, même si un filtre est appliqué pour n’afficher que les termes de recherche qui contiennent une valeur spécifique.

## Autres options de création de rapports  {#section_FEF85C7FC6E14755A6086AFFF36E0EB4}

En plus de réduire la période, le nombre de mesures et le nombre de ventilations d’un rapport, les instructions suivantes permettent d’accroître la fiabilité de la distribution de rapports :

* Utilisez l’entrepôt de données pour demander des rapports qui contiennent de nombreuses ventilations ou mesures. L’entrepôt de données est conçu pour générer ces types de rapports.
* Planifiez l’exécution des rapports pendant les heures creuses. Cela augmente la probabilité qu’un rapport soit renvoyé, car la file d’attente des requêtes d’une suite de rapports est plus susceptible d’être vide pendant ces périodes.
* Vous pouvez utiliser le créateur de rapports pour diviser les rapports en périodes et requêtes plus petites qui contiennent moins de mesures. Vous pouvez ensuite utiliser la fonctionnalité Excel native pour fusionner les données de diverses requêtes dans un seul rapport.

