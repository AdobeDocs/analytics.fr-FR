---
title: Mettre en œuvre Adobe Analytics à l’aide du SDK Web d’Adobe Experience Platform
description: Utilisez l’extension SDK Web dans la collecte de données Adobe Experience Platform pour envoyer des données à Adobe Analytics.
source-git-commit: 472faef9c6ef99d4e58f2f5a9a71ca8d058f0ee2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Mettre en œuvre Adobe Analytics à l’aide du SDK Web d’Adobe Experience Platform

Vous pouvez utiliser le [SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html) pour envoyer des données à Adobe Analytics. Cette méthode de mise en œuvre fonctionne en traduisant le [modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr) dans un format utilisé par Analytics.

Vous pouvez envoyer des données à Experience Edge directement à l’aide du SDK Web ou par l’intermédiaire de l’extension SDK Web dans les balises.

## SDK Web

Présentation générale des tâches de mise en oeuvre :

![Mise en oeuvre d’Adobe Analytics à l’aide du workflow SDK Web](../../assets/websdk-annotated.png)

| | Tâche | Plus d’informations | |-| —|—| | 1 | Vérifiez que vous avez **définition d’une suite de rapports**. | [Gestionnaire de suites de rapports](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Configuration de schémas et de jeux de données**. Pour normaliser la collecte de données à utiliser dans les applications qui utilisent Adobe Experience Platform, Adobe a créé la norme ouverte et documentée publiquement, Experience Data Model (XDM). | [Présentation de l’interface utilisateur des schémas](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=fr) et [Présentation de l’interface utilisateur des jeux de données](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=fr) | | 3 | **Création d’une couche de données** pour gérer le suivi des données sur votre site web. | [Création d’une couche de données](../../prepare/data-layer.md) | | 4 | **Installation de la version autonome prédéfinie**. Vous pouvez référencer la bibliothèque (`alloy.js`) sur le réseau de diffusion de contenu directement sur votre page ou téléchargez-le et hébergez-le sur votre propre infrastructure. Vous pouvez également utiliser le package NPM. | [Installation de la version autonome prédéfinie](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-2%3A-installing-the-prebuilt-standalone-version) et [Utilisation du package NPM](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-3%3A-using-the-npm-package)| | 5 | **Configuration d’un flux de données**. Un flux de données représente la configuration côté serveur lors de l’implémentation du SDK Web de Adobe Experience Platform. | [Configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 6 | **Ajout d’un service Adobe Analytics** à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics. | [Ajout d’un service Adobe Analytics à un flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 7 | **Configuration du SDK Web**. Assurez-vous que la bibliothèque que vous avez installée à l’étape 4 est correctement configurée avec l’identifiant de flux de données (anciennement appelé id de configuration Edge ).`edgeConfigId`), id d’organisation (`orgId`) et d’autres options disponibles. | [Configuration du SDK Web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=fr) | | 8 | **Exécuter les commandes** et/ou **suivi des événements**. Une fois que le code de base a été implémenté sur votre page web, vous pouvez commencer à exécuter des commandes et à effectuer le suivi des événements avec le SDK. | [Exécuter les commandes](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=en) et [Suivi des événements](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=en) | | 9 | **Étendez et validez votre implémentation** avant de le diffuser en production. | |



## Extension SDK web

Présentation générale des tâches de mise en oeuvre :

![Mise en oeuvre d’Adobe Analytics à l’aide du workflow d’extension du SDK Web](../../assets/websdk-extension-annotated.png)

| | Tâche | Plus d’informations | |-| —|—| | 1 | Vérifiez que vous avez **définition d’une suite de rapports**. | [Gestionnaire de suites de rapports](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Configuration de schémas et de jeux de données**. Pour normaliser la collecte de données à utiliser dans les applications qui utilisent Adobe Experience Platform, Adobe a créé la norme ouverte et documentée publiquement, Experience Data Model (XDM). | [Présentation de l’interface utilisateur des schémas](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=fr) et [Présentation de l’interface utilisateur des jeux de données](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=fr) | | 3 | **Création d’une couche de données** pour gérer le suivi des données sur votre site web. | [Création d’une couche de données](../../prepare/data-layer.md) | | 4 | **Configuration d’un flux de données**. Un flux de données représente la configuration côté serveur lors de l’implémentation du SDK Web de Adobe Experience Platform. | [Configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 5 | **Ajout d’un service Adobe Analytics** à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics. | [Ajout d’un service Adobe Analytics à un flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 6 | **Création d’une propriété de balise**. Les propriétés sont des conteneurs globaux utilisés pour référencer les données de la gestion des balises.| [Création ou configuration d’une propriété de balise pour le Web](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en#for-web) | | 7 | **Installation et configuration de l’extension SDK Web** dans la propriété de balise. Configurez l’extension SDK Web pour envoyer des données à la banque de données configurée à l’étape 4. | [Présentation de l’extension SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=en) | | 8 | **Itérer, valider et publier** en production. Ajoutez la propriété de balise à votre site web. Utilisez ensuite des éléments de données, des règles, etc., pour personnaliser votre mise en oeuvre. | [Présentation de la publication](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=fr) |



## Ressources supplémentaires

Les balises peuvent être hautement personnalisées. Découvrez comment tirer le meilleur parti d’Adobe Analytics en incluant les données appropriées dans votre mise en œuvre.

- [Documentation des balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr#) : découvrez le fonctionnement de l’interface et les extensions disponibles.

- [Documentation du SDK Web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=fr)
