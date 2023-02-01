---
title: Mise en oeuvre d’Adobe Analytics à l’aide de l’extension Analytics
description: Découvrez comment mettre en oeuvre Adobe Analytics à l’aide de balises et de l’extension Analytics
feature: Launch Implementation
source-git-commit: aef1d613437688b7eed704b227c41e4fbe4677dd
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 58%

---

# Mise en oeuvre d’Adobe Analytics à l’aide de l’extension Analytics

Au cours de la durée de vie d’Adobe Analytics, Adobe a proposé plusieurs méthodes différentes pour mettre en œuvre le code sur votre site pour la collecte de données. La méthode actuellement recommandée par l’Adobe consiste à utiliser des balises dans Adobe Experience Platform.

Les balises dans Adobe Experience Platform représentent une solution de gestion des balises qui vous permet de déployer le code Analytics parallèlement à d’autres exigences de balisage. Adobe propose des intégrations à d’autres solutions et produits et vous permet de déployer du code personnalisé. Toutes ces tâches peuvent être effectuées sans faire appel aux équipes de développement de votre entreprise pour mettre à jour le code de votre site.

Tous les clients disposant d’un contrat Adobe Experience Cloud actif peuvent utiliser les balises. Si vous n’êtes pas sûr d’y avoir accès, contactez l’un des administrateurs système Experience Cloud de votre entreprise.

Présentation générale des tâches de mise en oeuvre :



![Adobe Analytics à l’aide du workflow d’extension Analytics](../assets/analytics-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tâche</b></th><th style="width:35%"><b>Plus d’informations</b></th>
</tr>

<tr>
<td> 1</td>
<td>Vérifiez que vous avez <b>définition d’une suite de rapports</b>.</td>
<td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">Gestionnaire de suites de rapports</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Création d’une couche de données</b>pour gérer le suivi des données sur votre site web.</td>
<td>
<a href="../prepare/data-layer.md">Création d’une couche de données</a>
</td>
</tr>

<tr>
<td>3</td>
<td><b><b>Création d’une propriété de balise</b>. Les propriétés sont des conteneurs globaux utilisés pour référencer les données de la gestion des balises.</td>
<td><a ref="../launch/create-analytics-property.md">Création d’une propriété de balise Adobe Analytics</a></td>
</tr>

<tr>
<td>4</td><td><b>Installation de l’extension Analytics</b> dans la propriété tag . Configurez l’extension Analytics pour envoyer des données à Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=en">Présentation de lʼextension Adobe Analytics</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Déploiement dans un environnement de développement</b>. disposer d’un environnement dans lequel vous pouvez effectuer une itération sur le développement des balises ;</td>
<td><a href="./deploy-dev.md">Déploiement d’une mise en œuvre d’Analytics dans un environnement de développement</td>
</tr>

<tr>
<td>6</td> 
<td><b>Validation et publication en production</b>. Ajoutez la propriété de balise à votre site web. Utilisez ensuite des éléments de données, des règles, etc., pour personnaliser votre mise en oeuvre.</td>
<td><a href="./validate-publish-prod.md">Validation de la mise en œuvre d’un développement et publication en production</a></td>
</tr>

</table>

## Ressources supplémentaires

Les balises peuvent être hautement personnalisées. Découvrez comment tirer le meilleur parti d’Adobe Analytics en incluant les données appropriées dans votre mise en œuvre.

- [Documentation des balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr#) : découvrez le fonctionnement de l’interface et les extensions disponibles.

- [Variables de mise en œuvre](../vars/overview.md) : déterminez les variables que vous souhaitez envoyer aux serveurs de collecte de données.
