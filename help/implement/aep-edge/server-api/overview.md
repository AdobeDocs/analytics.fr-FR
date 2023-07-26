---
title: Mise en oeuvre d’Adobe Analytics à l’aide de l’API Adobe Experience Platform Edge Network Server
description: Utilisez l’API Adobe Experience Platform Edge Network Server pour envoyer des données à Adobe Analytics.
exl-id: 1ede95b7-4f17-4d69-aba6-62b253b6693a
feature: Implementation Basics
source-git-commit: 5ebc53e8706f60988b289df060be9b02b5dc778f
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 41%

---

# Mise en oeuvre d’Adobe Analytics à l’aide de l’API Adobe Experience Platform Edge Network Server

En règle générale, vous utilisez l’API Experience Platform Edge Network Server pour collecter des données à partir de périphériques tels que des appareils IoT, des décodeurs, des applications de bureau. Ensuite, envoyez ces données au réseau Edge, puis à des services comme Adobe Analytics.

Tenez également compte de l’API Edge Network Server lorsque vous avez besoin que des données sensibles soient collectées en toute sécurité et authentifiées sur l’ensemble du réseau. Voir [Authentification](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/authentication.html?lang=en) pour plus d’informations.

Présentation générale des tâches d’implémentation :

![Adobe Analytics avec le workflow d’extension Analytics](../../assets/edge-network-server-api.svg)

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
<td><b>Configurez un flux de données</b>. Un flux de données représente la configuration côté serveur lors de l’utilisation des API de l’API Adobe Experience Platform Edge Network.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr">Configurer un flux de données<a></td> 
</tr>

<tr>
<td>4</td>
<td><b>Mise en oeuvre et test de la collecte de données</b> à l’aide des données d’événement unique et des API de collecte de données d’événement par lot.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=en">Collecte de données à événement unique</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html?lang=en">Collecte de données d’événement par lots</a>
</tr>

<td>5</td>
<td><b>Ajoutez un service Adobe Analytics</b> à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=ens">Interagir avec Adobe Analytics</a></td>
</tr>


</table>

Voir [Documentation de l’API du serveur réseau Edge](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=fr), et un exemple [intégration avec Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=fr) pour plus d’informations.

