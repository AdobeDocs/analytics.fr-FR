---
title: Mettre en œuvre Adobe Analytics à l’aide du SDK Mobile d’Adobe Experience Platform
description: Utilisez l’extension Mobile SDK dans la Collecte de données Adobe Experience Platform pour envoyer des données à Adobe Analytics.
exl-id: 516e9a1e-caa7-4f8a-ab8c-6404e9242ccb
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/ooh8s8pNYbbsD9BmF48Nv3OyHN5JtDQonQw0Z1t4XXc'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
    internal-label: Mobile SDK
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 94%
---
# Mettre en œuvre Adobe Analytics à l’aide du SDK Mobile d’Adobe Experience Platform

Adobe Experience Platform Mobile SDK permet d’optimiser les solutions et services CX Enterprise d’Adobe dans vos applications mobiles. Il est disponible pour Android, iOS et différents frameworks de développement sur plusieurs plateformes. La configuration est gérée dans la Collecte de données Adobe Experience Platform.

>[!IMPORTANT]
>
>Une extension Adobe Analytics est également disponible dans la Collecte de données Adobe Experience Platform. Si vous installez cette extension, vous ne profitez pas de XDM ou d’Edge Network.

## SDK Adobe Experience Platform

Vue d’ensemble des tâches de mise en œuvre :

![Adobe Analytics avec le workflow d’extension Analytics](../../assets/mobilesdk-annotated.png)

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
<td><b>Configurez un flux de données</b>. Un train de données représente la configuration côté serveur lors de la mise en œuvre du SDK web Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr">Configurer un flux de données<a></td> 
</tr>

<td>3</td>
<td><b>Ajoutez un service Adobe Analytics</b> à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#analytics">Ajoutez un service Adobe Analytics à un flux de données.</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Créez une propriété mobile</b>. Une propriété est un conteneur que vous remplissez d’extensions, de règles, d’éléments de données et de bibliothèques.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/">Configurer une propriété mobile</a></tr>

<tr>
<td>5</td>
<td><b>Installez l’extension du réseau Edge d’Adobe Experience Platform</b> dans la propriété de balise mobile et configurez le flux de données dans l’extension.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/edge-network/">Réseau EDGE d²Adobe Experience Platform</a>
</tr>

<tr>
<td>6</td>
<td><b>Utilisez le code dans votre application</b> pour enregistrer les extensions nécessaires et charger votre configuration de balise.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">Définir la configuration</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Implémentez et testez la fonctionnalité</b> en combinant des éléments de données de la balise, des règles, des extensions supplémentaires et des appels API du SDK dans votre application. Inspectez, validez et déboguez la collecte de données et les expériences pour votre application mobile.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">Utiliser l’exemple d’application</a>
</tr>

<tr>
<td>8</td>
<td><b>Étendez et validez l’implémentation de votre application mobile</b> avant de la diffuser en production.</td>
<td></td> 
</tr>

</table>


## Extension Adobe Analytics.

Vue d’ensemble des tâches de mise en œuvre :

![Adobe Analytics avec le workflow d’extension Analytics](../../assets/mobilesdk-analytics-annotated.png)

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
<td><b>Installez l’extension Adobe Analytics</b> dans la propriété de balise mobile et configurez l’extension pour qu’elle pointe vers votre suite de rapports.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/adobe-analytics/">Extension Adobe Analytics pour la propriété mobile</a>
</tr>

<tr>
<td>3</td>
<td><b>Utilisez le code dans votre application</b> pour enregistrer les extensions nécessaires et charger votre configuration de balise.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">Définir la configuration</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Implémentez et testez la fonctionnalité</b> en combinant des éléments de données de la balise, des règles, des extensions supplémentaires et des appels API du SDK dans votre application. Inspectez, validez et déboguez la collecte de données et les expériences pour votre application mobile.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">Utiliser l’exemple d’application</a>
</tr>

<tr>
<td>5</td>
<td><b>Étendez et validez l’implémentation de votre application mobile</b> avant de la diffuser en production.</td>
<td></td> 
</tr>

</table>

## Ressources supplémentaires

- [Documentation sur les balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr#)

- [Documentation de Mobile SDK](https://developer.adobe.com/client-sdks/documentation/)
