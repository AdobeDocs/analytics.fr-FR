---
title: Mettre en œuvre Adobe Analytics à l’aide du SDK Web d’Adobe Experience Platform
description: Utilisez l’extension SDK Web dans la collecte de données Adobe Experience Platform pour envoyer des données à Adobe Analytics.
source-git-commit: 97bff355a5d9bb737d510221b63ba1321aaf5812
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 31%

---

# Mettre en œuvre Adobe Analytics à l’aide du SDK Web d’Adobe Experience Platform

Vous pouvez utiliser le [SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html) pour envoyer des données à Adobe Analytics. Cette méthode de mise en œuvre fonctionne en traduisant le [modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr) dans un format utilisé par Analytics.

Vous pouvez envoyer des données à Experience Edge directement à l’aide du SDK Web ou par l’intermédiaire de l’extension SDK Web dans les balises.

## SDK Web

Présentation générale des tâches de mise en oeuvre :

![Mise en oeuvre d’Adobe Analytics à l’aide du workflow SDK Web](../../assets/websdk-annotated.png)

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
<td><b>Création d’une couche de données</b> pour gérer le suivi des données sur votre site web.</td>
<td><a href="../../prepare/data-layer.md">Création d’une couche de données</a></td>
</tr>

<tr>
<td> 4</td>
<td><b>Installation de la version autonome prédéfinie</b>. Vous pouvez référencer la bibliothèque (<code>alloy.js</code>) sur le réseau de diffusion de contenu directement sur votre page ou téléchargez-le et hébergez-le sur votre propre infrastructure. Vous pouvez également utiliser le package NPM.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-2%3A-installing-the-prebuilt-standalone-version">Installation de la version autonome prédéfinie</a> et <a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-3%3A-using-the-npm-package">Utilisation du package NPM</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Configurer un flux de données</b>. Un flux de données représente la configuration côté serveur lors de l’implémentation du SDK Web de Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">Configurer un flux de données<a></td> 
</tr>

<td>6</td>
<td><b>Ajout d’un service Adobe Analytics</b> à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">Ajout d’un service Adobe Analytics à un flux de données</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Configuration du SDK Web</b>. Assurez-vous que la bibliothèque que vous avez installée à l’étape 4 est correctement configurée avec l’identifiant de flux de données (anciennement appelé id de configuration Edge ).<code>edgeConfigId</code>), id d’organisation (<code>orgId</code>) et d’autres options disponibles.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=fr">Configuration du SDK Web</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Exécuter les commandes</b> et/ou <b>suivi des événements</b>. Une fois que le code de base a été implémenté sur votre page web, vous pouvez commencer à exécuter des commandes et à effectuer le suivi des événements avec le SDK.
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=en">Exécuter les commandes</a> et <a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=en">Suivi des événements</a></td>
</tr>

<tr>
<td>9</td><td><b>Étendez et validez votre implémentation</b> avant de le diffuser en production.</td><td></td> 
</tr>
</table>


## Extension SDK web

Présentation générale des tâches de mise en oeuvre :

![Mise en oeuvre d’Adobe Analytics à l’aide du workflow d’extension du SDK Web](../../assets/websdk-extension-annotated.png)

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
<td><b>Création d’une couche de données</b> pour gérer le suivi des données sur votre site web.</td>
<td><a href="../../prepare/data-layer.md">Création d’une couche de données</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Configurer un flux de données</b>. Un flux de données représente la configuration côté serveur lors de l’implémentation du SDK Web de Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">Configurer un flux de données<a></td> 
</tr>

<tr>
<td>5</td> 
<td><b>Ajout d’un service Adobe Analytics</b> à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">Ajout d’un service Adobe Analytics à un flux de données</a></td>
</tr>

<tr>
<td>6</td>
<td><b>Création d’une propriété de balise</b>. Les propriétés sont des conteneurs globaux utilisés pour référencer les données de la gestion des balises.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en#for-web">Création ou configuration d’une propriété de balise pour le Web</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>Installation et configuration de l’extension SDK Web</b> dans la propriété de balise. Configurez l’extension SDK Web pour envoyer des données à la banque de données configurée à l’étape 4.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=en">Présentation de l’extension SDK Web d’Adobe Experience Platform</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Itérer, valider et publier</b> en production. Ajoutez la propriété de balise à votre site web. Utilisez ensuite des éléments de données, des règles, etc., pour personnaliser votre mise en oeuvre.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=fr">Présentation de la publication</a></td>
</tr>

</table>


## Ressources supplémentaires

Les balises peuvent être hautement personnalisées. Découvrez comment tirer le meilleur parti d’Adobe Analytics en incluant les données appropriées dans votre mise en œuvre.

- [Documentation des balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr#) : découvrez le fonctionnement de l’interface et les extensions disponibles.

- [Documentation du SDK Web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=fr)
