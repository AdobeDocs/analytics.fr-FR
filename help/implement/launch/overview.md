---
title: Implémenter Adobe Analytics à l’aide de l’extension Analytics
description: Découvrez comment implémenter Adobe Analytics à l’aide de balises et de l’extension Analytics.
feature: Launch Implementation
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
source-git-commit: bef853934683f647e05d42e1a751217c8f9b5dc4
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 95%

---

# Implémenter Adobe Analytics à l’aide de l’extension Analytics

Au cours de la durée de vie d’Adobe Analytics, Adobe a proposé plusieurs méthodes différentes pour implémenter le code sur votre site à des fins de collecte de données. La méthode actuellement recommandée par Adobe est d’utiliser des balises dans Adobe Experience Platform.

Les balises dans Adobe Experience Platform représentent une solution de gestion des balises qui vous permet de déployer le code Analytics parallèlement à d’autres exigences de balisage. Adobe propose des intégrations à d’autres solutions et produits et vous permet de déployer du code personnalisé. Toutes ces tâches peuvent être effectuées sans faire appel aux équipes de développement de votre entreprise pour mettre à jour le code de votre site.

Tous les clients disposant d’un contrat Adobe Experience Cloud actif peuvent utiliser les balises. Si vous ne savez pas si vous y avez accès, contactez l’administration système Experience Cloud de votre organisation.

Présentation générale des tâches d’implémentation :



![Comment mettre en oeuvre Adobe Analytics à l’aide du workflow d’extension Analytics, comme décrit dans cette section.](../assets/analytics-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tâche</b></th><th style="width:35%"><b>Informations supplémentaires</b></th>
</tr>

<tr>
<td> 1</td>
<td>Vérifiez que vous avez <b>défini une suite de rapports</b>.</td>
<td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">Gestionnaire de suites de rapports</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Créez une couche de données</b> pour gérer le suivi des données sur votre site web.</td>
<td>
<a href="../prepare/data-layer.md">Créer une couche de données</a>
</td>
</tr>

<tr>
<td>3</td>
<td><b><b>Créez une propriété de balise</b>. Les propriétés sont des conteneurs globaux utilisés pour référencer les données de la gestion des balises.</td>
<td><a ref="../launch/create-analytics-property.md">Créer une propriété de balise Adobe Analytics</a></td>
</tr>

<tr>
<td>4</td><td><b>Installez l’extension Analytics</b> dans la propriété de balise. Configurez l’extension Analytics pour envoyer des données à Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=fr">Présentation de lʼextension Adobe Analytics</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Déployer dans un environnement de développement</b> vous permet de dispose d’un environnement dans lequel vous pouvez effectuer une itération sur le développement des balises.</td>
<td><a href="./deploy-dev.md">Déployer une implémentation d’Analytics dans un environnement de développement</td>
</tr>

<tr>
<td>6</td> 
<td><b>Validez et publiez en production</b>. Ajoutez la propriété de balise à votre site web. Utilisez ensuite des éléments de données, des règles, etc., pour personnaliser votre implémentation.</td>
<td><a href="./validate-publish-prod.md">Valider l’implémentation d’un développement et publier en production</a></td>
</tr>

</table>

## Ressources supplémentaires

Les balises peuvent être hautement personnalisées. Découvrez comment tirer le meilleur parti d’Adobe Analytics en incluant les données appropriées dans votre mise en œuvre.

- [Documentation des balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr#) : découvrez le fonctionnement de l’interface et les extensions disponibles.

- [Variables d’implémentation](../vars/overview.md) : déterminez les variables que vous souhaitez envoyer aux serveurs de collecte de données.
