---
description: Les filtres URL internes identifient les référents que vous considérez comme internes à votre site. Ils permettent de compiler des données dans les rapports de sources de données et de filtrer le trafic interne.
seo-description: Les filtres URL internes identifient les référents que vous considérez comme internes à votre site. Ils permettent de compiler des données dans les rapports de sources de données et de filtrer le trafic interne.
seo-title: Filtres URL internes
solution: Analytics
title: Filtres URL internes
topic: Outils d’administration
uuid: 70868edb-208d-4dad-9401-70967468d40c
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Filtres URL internes

Les filtres URL internes identifient les référents que vous considérez comme internes à votre site. Ils permettent de compiler des données dans les rapports de sources de données et de filtrer le trafic interne.

Un référent, ou une page référente, est habituellement la page à partir de laquelle un visiteur arrive sur votre site. Pour éviter de biaiser les données, vous pouvez filtrer les référents. Les rapports excluent les référents filtrés du Rapport [](/help/components/c-variables/dimensionslist/reports-referrers.md)Référents, Rapport [Domaines](/help/components/c-variables/dimensionslist/reports-referring-domains.md)référents et autres rapports Méthodes de recherche.

Le plus souvent, les rapports de sources de trafic ne compilent aucune donnée car la liste Filtres URL internes n’est pas définie. Pour vérifier quels filtres URL internes ont été définis sur une suite de rapports, suivez les étapes ci-après. Pour éviter ce problème, supprimez la règle définissant un point (.) comme filtre, puis ajoutez votre propre site.

Un point est utilisé comme filtre URL interne par défaut afin d’autoriser la collecte des données dans le rapport Pages. Si les accès ne correspondent pas aux filtres URL internes, toutes les pages sont répertoriées comme Autres. Une URL contient toujours un point quelque part, ce qui garantit la génération du rapport Pages.
