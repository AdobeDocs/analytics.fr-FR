---
title: Mettre en œuvre Adobe Analytics à l’aide du SDK Web d’Adobe Experience Platform
description: Utilisez l’extension SDK Web dans la collecte de données Adobe Experience Platform pour envoyer des données à Adobe Analytics.
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
source-git-commit: d9948fbb63d44c851e08745c77af5618de84a89c
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 100%

---

# Mettre en œuvre Adobe Analytics à l’aide du SDK Web d’Adobe Experience Platform

Vous pouvez utiliser le [SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=fr) pour envoyer des données à Adobe Analytics. Cette méthode de mise en œuvre fonctionne en traduisant le [modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr) dans un format utilisé par Analytics.

Vous pouvez envoyer des données à Experience Edge directement à l’aide du SDK web ou par l’intermédiaire de l’extension SDK web dans les balises.

## SDK Web

Présentation générale des tâches d’implémentation :

![Implémentation d’Adobe Analytics à l’aide du workflow SDK web.](../../assets/websdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tâche</b></th><th style="width:35%"><b>Informations supplémentaires</b></th>
</tr>

<tr>
<td>1</td>
<td>Vérifiez que vous avez <b>défini une suite de rapports</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">Gestionnaire de suites de rapports</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configurez les schémas et les jeux de données</b>. Pour normaliser la collecte de données à utiliser dans les applications qui utilisent Adobe Experience Platform, Adobe a créé la norme ouverte et accessible au public, Modèle de données d’expérience (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=fr">Présentation de l’interface utilisateur des schémas</a> et <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=fr">Présentation de l’interface utilisateur des jeux de données</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Créez une couche de données</b> pour gérer le suivi des données sur votre site web.</td>
<td><a href="../../prepare/data-layer.md">Créer une couche de données</a></td>
</tr>

<tr>
<td> 4</td>
<td><b>Installez la version autonome prédéfinie</b>. Vous pouvez référencer la bibliothèque (<code>alloy.js</code>) sur le réseau CDN directement sur votre page ou la télécharger et l’héberger sur votre propre infrastructure. Vous pouvez également utiliser le package NPM.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=fr#option-2%3A-installing-the-prebuilt-standalone-version">Installer la version autonome prédéfinie</a> et <a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=fr#option-3-%3A-utilisation-du-package-npm">utiliser le package NPM</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Configurez un flux de données</b>. Un flux de données représente la configuration côté serveur lors de l’implémentation du SDK Web Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr">Configurer un flux de données<a></td> 
</tr>

<td>6</td>
<td><b>Ajoutez un service Adobe Analytics</b> à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr#analytics">Ajoutez un service Adobe Analytics à un flux de données.</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Configurez le SDK Web</b>. Assurez-vous que la bibliothèque que vous avez installée à l’étape 4 est correctement configurée avec l’ID de flux de données (anciennement appelé ID de configuration Edge(<code>edgeConfigId</code>)), l’ID d’organisation (<code>orgId</code>) et les autres options disponibles.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=fr">Configurer le SDK Web</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Exécutez les commandes</b> et/ou <b>suivez des événements</b>. Une fois le code de base implémenté sur votre page web, vous pouvez commencer à exécuter des commandes et à suivre des évènements à l’aide du SDK.
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=fr">Exécuter des commandes</a> et <a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=fr">suivre des événements</a></td>
</tr>

<tr>
<td>9</td><td><b>Étendez et validez votre implémentation</b> avant de la diffuser en production.</td><td></td> 
</tr>
</table>


## Extension SDK Web

Présentation générale des tâches d’implémentation :

![Implémentation d’Adobe Analytics à l’aide du workflow d’extension du SDK web.](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tâche</b></th><th style="width:35%"><b>Informations supplémentaires</b></th>
</tr>

<tr>
<td>1</td>
<td>Vérifiez que vous avez <b>défini une suite de rapports</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">Gestionnaire de suites de rapports</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configurez les schémas et les jeux de données</b>. Pour normaliser la collecte de données à utiliser dans les applications qui utilisent Adobe Experience Platform, Adobe a créé la norme ouverte et accessible au public, Modèle de données d’expérience (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=fr">Présentation de l’interface utilisateur des schémas</a> et <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=fr">Présentation de l’interface utilisateur des jeux de données</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Créez une couche de données</b> pour gérer le suivi des données sur votre site web.</td>
<td><a href="../../prepare/data-layer.md">Créer une couche de données</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Configurez un flux de données</b>. Un flux de données représente la configuration côté serveur lors de l’implémentation du SDK Web Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr">Configurer un flux de données<a></td> 
</tr>

<tr>
<td>5</td> 
<td><b>Ajoutez un service Adobe Analytics</b> à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr#analytics">Ajoutez un service Adobe Analytics à un flux de données.</a></td>
</tr>

<tr>
<td>6</td>
<td><b>Créez une propriété de balise</b>. Les propriétés sont des conteneurs globaux utilisés pour référencer les données de la gestion des balises.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=fr#pour-le-web">Créer ou configurer une propriété de balise pour le web</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>Installez et configurez l’extension SDK web</b> dans la propriété de balise. Configurez l’extension SDK web pour envoyer des données au flux de données configuré à l’étape 4.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=fr">Présentation de l’extension SDK Web d’Adobe Experience Platform</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Itérez, validez et publiez</b> en production. Ajoutez la propriété de balise à votre site web. Utilisez ensuite des éléments de données, des règles, etc., pour personnaliser votre implémentation.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=fr">Présentation de la publication</a></td>
</tr>

</table>


## Ressources supplémentaires

Les balises peuvent être hautement personnalisées. Découvrez comment tirer le meilleur parti d’Adobe Analytics en incluant les données appropriées dans votre mise en œuvre.

- [Documentation des balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr#) : découvrez le fonctionnement de l’interface et les extensions disponibles.

- [Documentation sur le SDK web d’Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=fr)
