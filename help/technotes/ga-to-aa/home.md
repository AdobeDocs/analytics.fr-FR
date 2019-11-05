---
title: Transition d’une plateforme d’analyse tierce vers Adobe Analytics
description: Découvrez les concepts clés pour obtenir des rapports destinés aux utilisateurs familiarisés avec d’autres plateformes, comme Google Analytics.
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Transition d’une plateforme d’analyse tierce vers Adobe Analytics

Ce guide présente les types de rapports courants qui vous aident à découvrir les concepts et processus de base dans Adobe Analytics, en vous concentrant sur les principales similarités et différences entre Adobe et d’autres outils courants. Ce guide s’adresse aux analystes qui connaissent bien les concepts de base des analyses numériques, mais qui ne connaissent pas Adobe Analytics. Cela suppose que l’entreprise dispose d’une implémentation opérationnelle qui envoie des données aux serveurs de collecte de données Adobe. Si votre entreprise n’a pas encore configuré de mise en oeuvre d’Adobe Analytics, commencez par le Guide [d’administration d’](/help/admin/admin-console/first-admin-guide.md)Adobe Analytics First Admin.

Google Analytics et Adobe Analytics sont des plates-formes puissantes qui permettent d’obtenir des informations précieuses sur les performances de votre site Web. Chacun possède sa propre architecture de traitement et son propre interface utilisateur, ce qui confère à chaque plateforme des avantages uniques. Ce guide a pour but d’aider un utilisateur expérimenté avec Google Analytics à se familiariser avec Adobe Analytics.

Dans Adobe Analytics, il existe deux méthodes principales pour extraire les rapports de base après connexion à Adobe Experience Cloud :

* **Rapports et analyses** est la méthode historique d’extraction des rapports de base. Le menu de gauche fournit une liste de rapports préfabriqués et permet à l’utilisateur d’accéder au rapport souhaité et d’obtenir des données. Les segments et les mesures peuvent fournir des personnalisations supplémentaires. Les utilisateurs expérimentés dans les rapports Google Analytics peuvent trouver cette disposition familière.
* **Analysis Workspace** est la méthode actuellement recommandée pour extraire la plupart des rapports. Le menu de gauche permet à l'utilisateur de faire glisser des composants pour créer son propre rapport. Il offre une plus grande liberté pour répondre aux besoins précis en matière de rapports. Les utilisateurs expérimentés dans la création de tableaux de bord et de rapports personnalisés Google Analytics peuvent trouver cette disposition familière.

La plupart des rapports peuvent être créés dans les rapports et analyses et dans Analysis Workspace. Cependant, certains rapports ne peuvent être extraits qu’à l’aide d’une plateforme ou d’une autre. Dans la plupart des cas, Adobe conseille d’utiliser Analysis Workspace, sauf si une fonction spécifique n’est disponible que dans les rapports et analyses.

## Chemin d’apprentissage recommandé

Adobe recommande de commencer par les principes de base absolus de l’obtention des données de rapport :

* [Création d’un rapport de base dans Analysis Workspace pour les utilisateurs de GA](reports/create-report.md)

Une fois que vous êtes familiarisé avec les composants d’Analysis Workspace, vous pouvez apprendre à recréer la plupart des rapports à l’aide des composants appropriés.

* [Création de rapports en temps réel dans Adobe Analytics](reports/realtime-reports.md)
* [Création de rapports Audience dans Adobe Analytics](reports/audience-reports.md)
* [Création de rapports d’acquisition dans Adobe Analytics](reports/acquisition-reports.md)
* [Création de rapports de comportement dans Adobe Analytics](reports/behavior-reports.md)
* [Création de rapports de conversion dans Adobe Analytics](reports/conversions-reports.md)

Après avoir appris à extraire des rapports, la compréhension des différences [de](processing-differences.md) traitement et d’architecture peut aider à concilier les différents nombres obtenus entre les plateformes. Une [FAQ](faq.md) est également disponible.
