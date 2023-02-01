---
title: Mettre en œuvre Adobe Analytics à l’aide du SDK Mobile d’Adobe Experience Platform
description: Utilisez l’extension SDK Mobile dans la collecte de données Adobe Experience Platform pour envoyer des données à Adobe Analytics.
source-git-commit: 97bff355a5d9bb737d510221b63ba1321aaf5812
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 30%

---

# Mettre en œuvre Adobe Analytics à l’aide du SDK Mobile d’Adobe Experience Platform

Le SDK Mobile Adobe Experience Platform permet d’optimiser les solutions et services Experience Cloud d’Adobe dans vos applications mobiles. Il est disponible pour Android™, iOS et divers frameworks de développement multiplateformes. La configuration est gérée via la collecte de données Adobe Experience Platform.
>[!IMPORTANT]
>
>Une extension Adobe Analytics est également disponible dans la collecte de données Adobe Experience Platform. Si vous installez cette extension, vous ne profitez pas de XDM ou du réseau Edge.

## SDK Adobe Experience Platform

Présentation générale des tâches de mise en oeuvre :

![Adobe Analytics à l’aide du workflow d’extension Analytics](../../assets/mobilesdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tâche</b></th><th style="width:35%"><b>Plus d’informations</b></th>
</tr>

<tr>
<td>1</td>
<td>Vérifiez que vous avez <b>définition d’une suite de rapports</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">Gestionnaire de suites de rapports</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configuration de schémas et de jeux de données</b>. Pour normaliser la collecte de données à utiliser dans les applications qui utilisent Adobe Experience Platform, Adobe a créé la norme ouverte et documentée publiquement, Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=fr">Présentation de l’interface utilisateur des schémas</a> et <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=fr">Présentation de l’interface utilisateur des jeux de données</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Configurer un flux de données</b>. Un flux de données représente la configuration côté serveur lors de l’implémentation du SDK Web de Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">Configurer un flux de données<a></td> 
</tr>

<td>4</td>
<td><b>Ajout d’un service Adobe Analytics</b> à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">Ajout d’un service Adobe Analytics à un flux de données</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Création d’une propriété mobile</b>. Une propriété est un conteneur que vous remplissez d’extensions, de règles, d’éléments de données et de bibliothèques.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/">Configuration d’une propriété mobile</a></tr>

<tr>
<td>6</td>
<td><b>Installation de l’extension Adobe Experience Platform Edge Network</b> dans la propriété de balise mobile et configurez le flux de données dans l’extension .</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/edge-network/">Adobe Experience Platform Edge Network</a>
</tr>

<tr>
<td>7</td>
<td><b>Utilisation du code dans votre application</b> pour enregistrer les extensions nécessaires et charger votre configuration de balise.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">Configuration</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Mise en oeuvre et test de la fonctionnalité</b> en combinant des éléments de données, des règles, des extensions supplémentaires et des appels d’API SDK dans votre application. Inspect, validez et déboguez la collecte de données et les expériences pour votre application mobile.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">Utilisation de l’exemple d’application</a>
</tr>

<tr>
<td>9</td>
<td><b>Étendre et valider la mise en oeuvre de votre application mobile</b> avant de le diffuser en production.</td>
<td></td> 
</tr>

</table>


## Extension Adobe Analytics.

Présentation générale des tâches de mise en oeuvre :

![Adobe Analytics à l’aide du workflow d’extension Analytics](../../assets/mobilesdk-analytics-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tâche</b></th><th style="width:35%"><b>Plus d’informations</b></th>
</tr>

<tr>
<td>1</td>
<td>Vérifiez que vous avez <b>définition d’une suite de rapports</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">Gestionnaire de suites de rapports</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configuration de schémas et de jeux de données</b>. Pour normaliser la collecte de données à utiliser dans les applications qui utilisent Adobe Experience Platform, Adobe a créé la norme ouverte et documentée publiquement, Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=fr">Présentation de l’interface utilisateur des schémas</a> et <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=fr">Présentation de l’interface utilisateur des jeux de données</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Installation de l’extension Adobe Analytics</b> dans la propriété de balise mobile et configurez l’extension pour qu’elle pointe vers votre suite de rapports.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/adobe-analytics/">Extension Adobe Analytics pour la propriété mobile</a>
</tr>

<tr>
<td>4</td>
<td><b>Utilisation du code dans votre application</b> pour enregistrer les extensions nécessaires et charger votre configuration de balise.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">Configuration</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Mise en oeuvre et test de la fonctionnalité</b> en combinant des éléments de données, des règles, des extensions supplémentaires et des appels d’API SDK dans votre application. Inspect, validez et déboguez la collecte de données et les expériences pour votre application mobile.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">Utilisation de l’exemple d’application</a>
</tr>

<tr>
<td>6</td>
<td><b>Étendre et valider la mise en oeuvre de votre application mobile</b> avant de le diffuser en production.</td>
<td></td> 
</tr>

</table>

## Ressources supplémentaires

- [Documentation sur les balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr#)

- [Documentation sur le SDK mobile](https://developer.adobe.com/client-sdks/documentation/)



