---
title: Transition d'une plateforme d'analyse tierce vers Adobe Analytics
description: Découvrez les concepts clés pour obtenir des rapports, destinés aux utilisateurs familiarisés avec d'autres plateformes, telles que Google Analytics.
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# Transition d'une plateforme d'analyse tierce vers Adobe Analytics

Ce guide présente les types de rapports courants qui vous permettent d'apprendre les concepts et les flux de travail principaux dans Adobe Analytics, en vous concentrant sur les similarités clés et les différences entre Adobe et d'autres outils populaires. Ce guide est destiné aux analystes familiarisés avec les concepts d'analyse numérique de base, mais qui sont nouveaux à Adobe Analytics. Il suppose que l'organisation dispose d'une implémentation opérationnelle qui envoie des données aux serveurs de collecte de données Adobe. If your organization has not yet set up an Adobe Analytics implementation, start with the [Adobe Analytics First Admin Guide](../../admin/admin-console/first-admin-guide.md).

Google Analytics et Adobe Analytics sont des plates-formes puissantes pour obtenir des informations précieuses sur les performances de votre site Web. Chacun dispose de son propre architecture de traitement et d'une interface utilisateur, offrant ainsi des avantages uniques à chaque plate-forme. Ce guide vise à aider un utilisateur à accéder à Google Analytics avec Google Analytics.

Dans Adobe Analytics, il existe deux manières principales d'extraire les rapports de base après la connexion à Adobe Experience Cloud :

* **Rapports et analyses** est la méthode historique permettant d'extraire des rapports de base. Le menu gauche fournit une liste des rapports préfabriqués et permet à l'utilisateur de naviguer jusqu'à un rapport souhaité et d'obtenir des données. Les segments et les mesures peuvent fournir des personnalisations supplémentaires. Cette disposition est familiarisée avec les utilisateurs familiarisés avec les rapports Google Analytics.
* **Analysis Workspace** est la méthode recommandée actuellement pour extraire la plupart des rapports. Le menu de gauche permet à l'utilisateur de faire glisser des composants pour créer leur propre rapport. Elle offre beaucoup plus de liberté pour répondre aux besoins exacts de rapports. Cette disposition est familiarisée avec les utilisateurs familiarisés avec la création des tableaux de bord Google Analytics et des rapports personnalisés.

La plupart des rapports peuvent être créés dans les rapports et analyses et dans Analysis Workspace. Toutefois, certains rapports ne peuvent être extraits qu'à l'aide d'une plateforme ou de l'autre. Dans la plupart des cas, Adobe recommande d'utiliser Analysis Workspace, sauf si une fonctionnalité spécifique est disponible uniquement dans les rapports et analyses.

## Chemin d'apprentissage recommandé

Adobe recommande de commencer par les principes de base absolus d'obtention des données de rapport :

* [Création d'un rapport de base dans Analysis Workspace pour les utilisateurs GA](reports/create-report.md)

Une fois que vous êtes familiarisé avec les composants d'Analysis Workspace, vous pouvez apprendre à recréer la plupart des rapports à l'aide des composants appropriés.

* [Créer des rapports en temps réel dans Adobe Analytics](reports/realtime-reports.md)
* [Création de rapports d'audience dans Adobe Analytics](reports/audience-reports.md)
* [Création de rapports d'acquisition dans Adobe Analytics](reports/acquisition-reports.md)
* [Création de rapports de comportement dans Adobe Analytics](reports/behavior-reports.md)
* [Création de rapports Conversions dans Adobe Analytics](reports/conversions-reports.md)

After learning to pull reports, understanding [processing and architecture differences](processing-differences.md) can help reconcile the different numbers obtained between platforms. [Une FAQ](faq.md) est également disponible.
