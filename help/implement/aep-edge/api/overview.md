---
title: Mise en œuvre d’Adobe Analytics à l’aide de l’API Adobe Experience Platform Edge Network
description: Utilisez l’API Adobe Experience Platform Edge Network pour envoyer des données à Adobe Analytics.
exl-id: 1ede95b7-4f17-4d69-aba6-62b253b6693a
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/lvnplKx6dPwmmbZWgSShGvZXD2TtUoigi-HNiKutZSg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 332
ht-degree: 43%

---

# Mise en œuvre d’Adobe Analytics à l’aide de l’API Adobe Experience Platform Edge Network

En règle générale, vous utilisez l’API Experience Platform Edge Network pour collecter des données côté serveur plutôt que côté client, et lors de la collecte de données à partir d’appareils tels que les appareils IoT, les décodeurs et les applications de bureau. Vous envoyez ensuite ces données au réseau Edge et à des services tels qu’Adobe Analytics.

Tenez également compte de l’API Edge Network lorsque vous avez besoin que les données sensibles soient collectées en toute sécurité et authentifiées sur le réseau. Voir [Authentification](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/authentication.html) pour plus d’informations.

Présentation générale des tâches d’implémentation :

![Adobe Analytics avec le workflow d’extension Analytics](../../assets/edge-network-server-api-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tâche</b></th><th style="width:35%"><b>Informations supplémentaires</b></th>
</tr>

<tr>
<td>1</td>
<td>Vérifiez que vous avez <b>défini une suite de rapports</b>.</td>
<td><a href="../../../admin/tools/manage-rs/report-suites-admin.md">Gestionnaire de suites de rapports</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configurer des schémas</b>. Pour normaliser la collecte de données à utiliser dans les applications qui utilisent Adobe Experience Platform, Adobe a créé la norme ouverte et accessible au public, Modèle de données d’expérience (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=fr">Présentation de l’interface utilisateur des schémas</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Configurez un flux de données</b>. Un flux de données représente la configuration côté serveur lors de l’utilisation des API de l’API Adobe Experience Platform Edge Network.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr">Configurer un flux de données<a></td> 
</tr>

<tr>
<td>4</td>
<td><b>Implémentez et testez la collecte de données</b> à l’aide des API de collecte de données d’événements uniques et par lots.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=fr">Collecte de données d’événement unique</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html?lang=fr">Collecte de données d’événement par lots</a>
</tr>

<td>5</td>
<td><b>Ajoutez un service Adobe Analytics</b> à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=fr">Interagir avec Adobe Analytics</a></td>
</tr>


</table>

Pour plus d’informations, consultez la [documentation de l’API &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=fr).

