---
title: Mettre en œuvre Adobe Analytics à l’aide du SDK Mobile d’Adobe Experience Platform
description: Utilisez l’extension SDK Mobile dans la collecte de données Adobe Experience Platform pour envoyer des données à Adobe Analytics.
source-git-commit: e6b40881a543b43c03b612c7e7b0d9bd09f44c0d
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 20%

---

# Mettre en œuvre Adobe Analytics à l’aide du SDK Mobile d’Adobe Experience Platform

Le SDK Mobile Adobe Experience Platform permet d’optimiser les solutions et services Experience Cloud d’Adobe dans vos applications mobiles. Il est disponible pour Android™, iOS et divers frameworks de développement multiplateformes. La configuration est gérée via la collecte de données Adobe Experience Platform.
>[!IMPORTANT]
>
>Une extension Adobe Analytics est également disponible dans la collecte de données Adobe Experience Platform. Si vous installez cette extension, vous ne profitez pas de XDM ou du réseau Edge.

## SDK Adobe Experience Platform

Présentation générale des tâches de mise en oeuvre :

![Adobe Analytics à l’aide du workflow d’extension Analytics](../../assets/mobilesdk-annotated.png)

|<div style="width:20px"></div>| Tâche | Plus d’informations | |-| —|—| | 1 | Vérifiez que vous avez **définition d’une suite de rapports**. | [Gestionnaire de suites de rapports](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Configuration des schémas et des jeux de données**. Pour normaliser la collecte de données à utiliser dans les applications qui utilisent Adobe Experience Platform, Adobe a créé la norme ouverte et documentée publiquement, Experience Data Model (XDM). | [Configuration des schémas et des jeux de données](https://developer.adobe.com/client-sdks/documentation/getting-started/set-up-schemas-and-datasets/) | | 3 | **Configuration d’un flux de données**. Un flux de données représente la configuration côté serveur lors de l’implémentation du SDK Web de Adobe Experience Platform. | [Configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 4 | **Ajout d’un service Adobe Analytics** à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics. | [Ajout d’un service Adobe Analytics à un flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 5 | **Création d’une propriété mobile**. Une propriété est un conteneur que vous remplissez d’extensions, de règles, d’éléments de données et de bibliothèques. | [Configuration d’une propriété mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/) | | 6 | **Installation de l’extension Adobe Experience Platform Edge Network** dans la propriété de balise mobile et configurez le flux de données dans l’extension . | [Adobe Experience Platform Edge Network](https://developer.adobe.com/client-sdks/documentation/edge-network/) | | 7 | **Utilisation du code dans votre application** pour enregistrer les extensions nécessaires et charger votre configuration de balise. | [Configuration](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration) | | 8 | **Mise en oeuvre et test de la fonctionnalité** en combinant des éléments de données, des règles, des extensions supplémentaires et des appels d’API SDK dans votre application. Inspect, validez et déboguez la collecte de données et les expériences pour votre application mobile. | [Utilisation de l’exemple d’application](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application) | | 9 | **Étendre et valider la mise en oeuvre de votre application mobile** avant de le diffuser en production. | |


## Extension Adobe Analytics.

Présentation générale des tâches de mise en oeuvre :

![Adobe Analytics à l’aide du workflow d’extension Analytics](../../assets/mobilesdk-analytics-annotated.png)

|<div style="width:20px"></div> | Tâche | Plus d’informations | |-| —|—| | 1 | Vérifiez que vous avez **définition d’une suite de rapports**. | [Gestionnaire de suites de rapports](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Création d’une propriété mobile**. Une propriété est un conteneur que vous remplissez d’extensions, de règles, d’éléments de données et de bibliothèques. | [Configuration d’une propriété mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/) | | 3 | **Installation de l’extension Adobe Analytics** dans la propriété de balise mobile et configurez l’extension pour qu’elle pointe vers votre suite de rapports. | [Extension Adobe Analytics pour la propriété mobile](https://developer.adobe.com/client-sdks/documentation/adobe-analytics/) | | 4 | **Utilisation du code dans votre application** pour enregistrer les extensions nécessaires et charger votre configuration de balise. | [Configuration](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration) | | 5 | **Mise en oeuvre et test de la fonctionnalité** en combinant des éléments de données, des règles, des extensions supplémentaires et des appels d’API SDK dans votre application. Inspect, validez et déboguez la collecte de données et les expériences pour votre application mobile. | [Utilisation de l’exemple d’application](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application) | | 6 | **Étendre et valider la mise en oeuvre de votre application mobile** avant de le diffuser en production. | |

## Ressources supplémentaires

- [Documentation sur les balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr#)

- [Documentation sur le SDK mobile](https://developer.adobe.com/client-sdks/documentation/)



