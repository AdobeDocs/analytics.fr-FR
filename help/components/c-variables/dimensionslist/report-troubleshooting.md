---
description: Adobe Analytics offre une interface de création de rapports souple qui permet de générer un large éventail de rapports complexes. Bien que la plupart des rapports soient générés très rapidement, vous pouvez rencontrer des rapports en dépassement de délai ou dont la génération a échoué. Pour permettre d’éviter les échecs de génération de rapport, cette rubrique présente de nombreux facteurs qui affectent la vitesse de génération des rapports. La connaissance de ces informations peut vous permettre de structurer les rapports de manière à ce qu’ils soient moins plus susceptibles d’échouer.
keywords: best practices;failure;timeout;troubleshooting;slow
title: Bonnes pratiques et dépannage de la création de rapports
topic: Reports
uuid: d4eef0a3-1d26-4460-8a2b-962001c9f846
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Bonnes pratiques et dépannage de la création de rapports

Adobe Analytics offre une interface de création de rapports souple qui permet de générer un large éventail de rapports complexes. Bien que la plupart des rapports soient générés très rapidement, vous pouvez rencontrer des rapports en dépassement de délai ou dont la génération a échoué. Pour permettre d’éviter les échecs de génération de rapport, cette rubrique présente de nombreux facteurs qui affectent la vitesse de génération des rapports. La connaissance de ces informations peut vous permettre de structurer les rapports de manière à ce qu’ils soient moins plus susceptibles d’échouer.

>[!Note] :
>ces recommandations s’appliquent à Reports &amp; Analytics, à Ad Hoc Analysis et à Report Builder.
>Elles ne s’appliquent pas à Analysis Workspace, qui possède son propre ensemble de [bonnes pratiques](/help/analyze/analysis-workspace/optimizing-performance.md). Elles ne s’appliquent pas non plus aux [bonnes pratiques](https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse_bp.html) de Data Warehouse. Un ensemble supplémentaire de
>[bonnes pratiques](https://marketing.adobe.com/developer/en_US/get-started/best-practices/c-best-practices) est disponible dans l’API de création de rapports d’Adobe Analytics.

## Délais d’expiration des rapports et file d’attente des demandes {#section_A42AD7E487C749B7B879BAFA814FFEF9}

**Délais d’expiration**

Un rapport est ventilé en plusieurs demandes (une par ventilation) et chaque demande est soumise à un délai d’expiration spécifique. Des délais d’expiration plus longs sont accordés aux rapports planifiés. Ainsi, ces derniers ont plus de chance de succès que les rapports générés directement dans une interface utilisateur.

**File d’attente des suites de rapports**

Chaque suite de rapports conserve une file d’attente distincte de demandes. Si de nombreux rapports sont demandés simultanément, même en provenance d’utilisateurs distincts, un faible nombre de rapports sont générés simultanément. Lorsque les rapports se terminent, les rapports restants sont générés dans l’ordre dans lequel ils sont reçus. En conséquence, si un grand nombre de rapports complexes se trouvent déjà dans la file d’attente des suites de rapports, un rapport qui est habituellement créé rapidement peut expirer.

## Facteurs qui affectent la vitesse des rapports {#section_6BA937EB6CEC4CBCB71FAAD32F031DC2}

Les facteurs suivants contribuent à rallonger le délai de génération des rapports. L’accroissement de l’un de ces facteurs peut ne pas résulter en un dépassement du délai d’expiration pour un rapport spécifique mais il peut retarder d’autres rapports dans la file d’attente des suites de rapports et provoquer un dépassement de délai du rapport suivant.

**Période des rapports**

Le facteur le plus important qui affecte le délai de génération des rapports est le nombre de mois demandé. La réduction du nombre de mois de trois à un diminue significativement le délai de génération mais la réduction de la période d’un mois à une semaine n’a pas un impact important sur le délai de génération.

**Nombre de mesures**

Alors que le nombre de mesures augmente, le délai d’exécution du rapport augmente. La suppression des mesures améliore souvent le délai de génération des rapports.

**Nombre de ventilations**

Dans un rapport, chaque ventilation représente une demande distincte. Alors que des demandes individuelles peuvent se terminer rapidement, l’exécution de milliers de ventilations dans un seul rapport peut ralentir de manière significative le délai de génération des rapports et affecter la file d’attente de la suite de rapports.

**Complexité des segments**

Les segments qui tiennent compte de plusieurs dimensions ou qui comportent de nombreuses règles (24+) augmentent l’impact du traitement et le délai de génération des rapports.

**Nombre de valeurs uniques**

Les rapports qui contiennent des centaines de milliers de valeurs uniques sont générés plus lentement que les rapports qui contiennent moins de valeurs uniques, même si le segment ou le filtre réduit le nombre de valeurs qui apparaissent finalement dans le rapport. Par exemple, un rapport qui affiche des termes de recherche est généré habituellement plus lentement que les autres rapports, même si un filtre est appliqué afin d’afficher uniquement les termes de recherche qui contiennent une valeur spécifique.

## Autres options de création de rapports {#section_FEF85C7FC6E14755A6086AFFF36E0EB4}

En plus de réduire la période, le nombre de mesures et le nombre de ventilations d’un rapport, les instructions suivantes permettent d’accroître la fiabilité de la distribution de rapports :

* Utilisez Data Warehouse pour demander des rapports qui contiennent de nombreuses ventilations ou mesures. Data Warehouse est conçu pour générer ces types de rapports.
* Planifiez les rapports pour qu’ils s’exécutent aux heures creuses. Cela augmente la probabilité d’un retour de rapport puisque la file d’attente des demandes d’une suite de rapports sera vraisemblablement vide aux heures creuses.
* Vous pouvez utiliser le Report Builder pour ventiler les rapports en périodes et demandes plus petites qui contiennent moins de mesures. Vous pouvez alors utiliser une fonctionnalité Excel native pour fusionner les données provenant de différentes demandes dans un seul rapport.

