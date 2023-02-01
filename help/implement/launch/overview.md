---
title: Mise en oeuvre d’Adobe Analytics à l’aide de l’extension Analytics
description: Découvrez comment mettre en oeuvre Adobe Analytics à l’aide de balises et de l’extension Analytics
feature: Launch Implementation
source-git-commit: 472faef9c6ef99d4e58f2f5a9a71ca8d058f0ee2
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 48%

---

# Mise en oeuvre d’Adobe Analytics à l’aide de l’extension Analytics

Au cours de la durée de vie d’Adobe Analytics, Adobe a proposé plusieurs méthodes différentes pour mettre en œuvre le code sur votre site pour la collecte de données. La méthode actuellement recommandée par l’Adobe consiste à utiliser des balises dans Adobe Experience Platform.

Les balises dans Adobe Experience Platform représentent une solution de gestion des balises qui vous permet de déployer le code Analytics parallèlement à d’autres exigences de balisage. Adobe propose des intégrations à d’autres solutions et produits et vous permet de déployer du code personnalisé. Toutes ces tâches peuvent être effectuées sans faire appel aux équipes de développement de votre entreprise pour mettre à jour le code de votre site.

Tous les clients disposant d’un contrat Adobe Experience Cloud actif peuvent utiliser les balises. Si vous n’êtes pas sûr d’y avoir accès, contactez l’un des administrateurs système Experience Cloud de votre entreprise.

Présentation générale des tâches de mise en oeuvre :

![Adobe Analytics à l’aide du workflow d’extension Analytics](../assets/analytics-extension-annotated.png)

| | Tâche | Plus d’informations | |-| —|—| | 1 | Vérifiez que vous avez **définition d’une suite de rapports**. | [Gestionnaire de suites de rapports](../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Création d’une couche de données** pour gérer le suivi des données sur votre site web. | [Création d’une couche de données](../prepare/data-layer.md) | | 3 | **Création d’une propriété de balise**. Les propriétés sont des conteneurs globaux utilisés pour référencer les données de la gestion des balises.| [Création d’une propriété de balise Adobe Analytics](../launch/create-analytics-property.md) | | 4 | **Installation de l’extension Analytics** dans la propriété tag . Configurez l’extension Analytics pour envoyer des données à Adobe Analytics. | [Présentation de l’extension Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=en) | | 5 | **Déploiement dans un environnement de développement**. disposer d’un environnement dans lequel vous pouvez effectuer une itération sur le développement des balises ; | [Déploiement d’une mise en oeuvre Analytics dans un environnement de développement](./deploy-dev.md) | | 6 | **Validation et publication en production**. Ajoutez la propriété de balise à votre site web. Utilisez ensuite des éléments de données, des règles, etc., pour personnaliser votre mise en oeuvre.| [Validation de l’implémentation d’un développement et publication en production](./validate-publish-prod.md) |

## Ressources supplémentaires

Les balises peuvent être hautement personnalisées. Découvrez comment tirer le meilleur parti d’Adobe Analytics en incluant les données appropriées dans votre mise en œuvre.

- [Documentation des balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr#) : découvrez le fonctionnement de l’interface et les extensions disponibles.

- [Variables de mise en œuvre](../vars/overview.md) : déterminez les variables que vous souhaitez envoyer aux serveurs de collecte de données.
