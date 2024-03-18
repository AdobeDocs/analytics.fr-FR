---
title: Mettre en œuvre Adobe Analytics à l’aide du SDK Web d’Adobe Experience Platform
description: Utilisez l’extension SDK Web dans la collecte de données Adobe Experience Platform pour envoyer des données à Adobe Analytics.
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 10ecae46424758fc5b19b58b733b49bb23cda222
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 72%

---

# Mettre en œuvre Adobe Analytics à l’aide du SDK Web d’Adobe Experience Platform

Vous pouvez utiliser le [SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html) pour envoyer des données à Adobe Analytics. Cette méthode de mise en oeuvre fonctionne en traduisant la variable [Modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr) dans un format utilisé par Analytics. Vous pouvez envoyer des données au réseau Adobe Experience Platform Edge à l’aide de la bibliothèque JavaScript du SDK Web ou de l’extension de balise du SDK Web.

## SDK Web

Présentation générale des tâches d’implémentation :

![Comment mettre en oeuvre Adobe Analytics à l’aide du workflow SDK Web, comme décrit dans cette section.](../../assets/websdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tâche</b></th><th style="width:35%"><b>Informations supplémentaires</b></th>
</tr>

<tr>
<td>1</td>
<td>Vérifiez que vous avez <b>défini une suite de rapports</b>.</td>
<td><a href="/help/admin/admin/c-manage-report-suites/report-suites-admin.md">Gestionnaire de suites de rapports</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configuration de schémas</b>. Pour normaliser la collecte de données à utiliser dans les applications qui utilisent Adobe Experience Platform, Adobe a créé la norme ouverte et accessible au public, Modèle de données d’expérience (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=fr">Présentation de l’interface utilisateur des schémas</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Créez une couche de données</b> pour gérer le suivi des données sur votre site web.</td>
<td><a href="../../prepare/data-layer.md">Créer une couche de données</a></td>
</tr>

<tr>
<td> 4</td>
<td><b>Installez la version autonome prédéfinie</b>. Vous pouvez référencer la bibliothèque (<code>alloy.js</code>) sur le réseau CDN directement sur votre page ou la télécharger et l’héberger sur votre propre infrastructure. Vous pouvez également utiliser le package NPM.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/library.html">Installer la version autonome prédéfinie</a> et <a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/npm.html">utiliser le package NPM</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Configurez un flux de données</b>. Un flux de données représente la configuration côté serveur lors de l’implémentation du SDK Web Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr">Configurer un flux de données<a></td> 
</tr>

<td>6</td>
<td><b>Ajoutez un service Adobe Analytics</b> à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics et à quelle(s) suite(s) de rapports en particulier.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#analytics">Ajoutez un service Adobe Analytics à un flux de données.</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Configurez le SDK Web</b>. Assurez-vous que la bibliothèque que vous avez installée à l’étape 4 est correctement configurée avec l’identifiant de flux de données (anciennement appelé id de configuration Edge ).<code>edgeConfigId</code>), id de l’organisation (<code>orgId</code>) et d’autres options disponibles. Assurez-vous que la correspondance des variables est correcte. </td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/configure/overview.html">Configuration du SDK Web</a><br/><a href="../xdm-var-mapping.md">Mappage des variables d’objet XDM</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Exécutez les commandes</b> et/ou <b>suivez des événements</b>. Une fois le code de base implémenté sur votre page web, vous pouvez commencer à exécuter des commandes et à suivre des évènements à l’aide du SDK.
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/sendevent/overview.html">Envoi d’événements</a></td>
</tr>

<tr>
<td>9</td><td><b>Étendez et validez votre implémentation</b> avant de la diffuser en production.</td><td></td> 
</tr>
</table>


## Extension SDK Web

Présentation générale des tâches d’implémentation :

![Comment mettre en oeuvre Adobe Analytics à l’aide du workflow d’extension du SDK Web, comme décrit dans cette section.](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tâche</b></th><th style="width:35%"><b>Informations supplémentaires</b></th>
</tr>

<tr>
<td>1</td>
<td>Vérifiez que vous avez <b>défini une suite de rapports</b>.</td>
<td><a href="/help/admin/admin/c-manage-report-suites/report-suites-admin.md">Gestionnaire de suites de rapports</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configuration de schémas</b>. Pour normaliser la collecte de données à utiliser dans les applications qui utilisent Adobe Experience Platform, Adobe a créé la norme ouverte et accessible au public, Modèle de données d’expérience (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=fr">Présentation de l’interface utilisateur des schémas</a></td>
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
<td><b>Ajoutez un service Adobe Analytics</b> à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics et à quelle(s) suite(s) de rapports en particulier.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#analytics">Ajoutez un service Adobe Analytics à un flux de données.</a></td>
</tr>

<tr>
<td>6</td>
<td><b>Créez une propriété de balise</b>. Les propriétés sont des conteneurs globaux utilisés pour référencer les données de la gestion des balises.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html#for-web">Créer ou configurer une propriété de balise pour le web</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>Installez et configurez l’extension SDK web</b> dans la propriété de balise. Configurez l’extension SDK web pour envoyer des données au flux de données configuré à l’étape 4.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=fr">Présentation de l’extension SDK Web d’Adobe Experience Platform</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Itérez, validez et publiez</b> en production. Incorporez le code pour inclure votre propriété de balise aux pages de votre site web. Utilisez ensuite des éléments de données, des règles, etc., pour personnaliser votre implémentation.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html#embed-code">Code incorporé</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=fr">Présentation de la publication</a></td>
</tr>

</table>


## Ressources supplémentaires

Les balises peuvent être hautement personnalisées. Découvrez comment tirer le meilleur parti d’Adobe Analytics en incluant les données appropriées dans votre mise en œuvre.

- [Documentation des balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr#) : découvrez le fonctionnement de l’interface et les extensions disponibles.

- [Documentation sur le SDK web d’Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=fr)
