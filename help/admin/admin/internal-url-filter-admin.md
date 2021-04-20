---
description: Les filtres URL internes identifient les référents que vous considérez comme internes à votre site. Ils permettent de compiler des données dans les rapports de sources de données et de filtrer le trafic interne.
title: Filtres URL internes
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 100%

---

# Filtres URL internes

**[!UICONTROL Admin > Suite de rapports > Modifier les paramètres > Général > Filtres URL internes > Ajouter un filtre]**

Les filtres URL internes identifient les référents que vous considérez comme internes à votre site. Ils permettent de compiler des données dans les rapports de sources de données et de filtrer le trafic interne.

Un référent, ou une page référente, est habituellement la page à partir de laquelle un visiteur arrive sur votre site. Pour éviter de biaiser les données, vous pouvez filtrer les référents. Les rapports excluent les référents filtrés de la dimension [Référent](/help/components/dimensions/referrer.md), de la dimension [domaines référents](/help/components/dimensions/referring-domain.md) et d’autres dimensions de source de trafic.

Le plus souvent, les rapports de sources de trafic ne compilent aucune donnée car la liste Filtres URL internes n’est pas définie. Pour vérifier quels filtres URL internes ont été définis sur une suite de rapports, suivez les étapes ci-après. Pour éviter ce problème, supprimez la règle définissant un point (.) comme filtre, puis ajoutez votre propre site.

Un point est utilisé comme filtre URL interne par défaut afin d’autoriser la collecte des données dans le rapport Pages. Si les accès ne correspondent pas aux filtres URL internes, toutes les pages sont répertoriées comme Autres. Une URL contient toujours un point quelque part, ce qui garantit la génération du rapport Pages.
