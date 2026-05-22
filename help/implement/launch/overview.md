---
title: Implémenter Adobe Analytics à l’aide de l’extension Analytics
description: Découvrez comment implémenter Adobe Analytics à l’aide de balises et de l’extension Analytics.
feature: Tags
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/bnn0eqUbhHvQL2YPd1qVa9cSWWvGbAAae33IyC-w9kA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 396
ht-degree: 69%

---

# Implémenter Adobe Analytics à l’aide de l’extension Analytics

Au cours de la durée de vie d’Adobe Analytics, Adobe a proposé plusieurs méthodes différentes pour implémenter le code sur votre site à des fins de collecte de données. La méthode actuellement recommandée par Adobe est d’utiliser [Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr) dans Adobe Experience Platform.

Les balises dans Adobe Experience Platform représentent une solution de gestion des balises qui vous permet de déployer le code Analytics parallèlement à d’autres exigences de balisage. Adobe propose des intégrations à d’autres solutions et produits et vous permet de déployer du code personnalisé. Toutes ces tâches peuvent être effectuées sans faire appel aux équipes de développement de votre entreprise pour mettre à jour le code de votre site.

Tous les clients disposant d’un contrat Adobe CX Enterprise actif peuvent utiliser les balises. Si vous ne savez pas si vous y avez accès, contactez l’administrateur système CX Enterprise de votre entreprise.

Présentation générale des tâches d’implémentation :



![Comment mettre en œuvre Adobe Analytics à l’aide du workflow d’extension Analytics, comme décrit dans cette section.](../assets/analytics-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tâche</b></th><th style="width:35%"><b>Informations supplémentaires</b></th>
</tr>

<tr>
<td> 1</td>
<td>Vérifiez que vous avez <b>défini une suite de rapports</b>.</td>
<td><a href="../../admin/tools/manage-rs/report-suites-admin.md">Gestionnaire de suites de rapports</a></td>
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
<td><b><b>Créer une propriété de balise</b>. Les propriétés sont des conteneurs globaux utilisés pour référencer les données de la gestion des balises.</td>
<td><a href="../launch/create-analytics-property.md">Créer une propriété de balise Adobe Analytics</a></td>
</tr>

<tr>
<td>4</td><td><b>Installez l’extension Analytics</b> dans la propriété de balise. Configurez l’extension Analytics pour envoyer des données à Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=fr">Présentation de lʼextension Adobe Analytics</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Déploiement dans un environnement de développement</b>. disposer d’un environnement dans lequel vous pouvez effectuer une itération sur le développement des balises ;</td>
<td><a href="./deploy-dev.md">Déployer une implémentation d’Analytics dans un environnement de développement</td>
</tr>

<tr>
<td>6</td> 
<td><b>Validez et publiez en production</b>. Code incorporé permettant d’inclure la propriété de balise dans les pages de votre site web. Utilisez ensuite des éléments de données, des règles, etc., pour personnaliser votre implémentation.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html#embed-code">Code incorporé</a><br/><a href="./validate-publish-prod.md">Validez une implémentation de développement et publiez-la en production</a></td>
</tr>

</table>

## Ressources supplémentaires

Les balises peuvent être hautement personnalisées. Découvrez comment tirer le meilleur parti d’Adobe Analytics en incluant les données appropriées dans votre mise en œuvre.

- [Documentation des balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr#) : découvrez le fonctionnement de l’interface et les extensions disponibles.

- [Variables d’implémentation](../vars/overview.md) : déterminez les variables que vous souhaitez envoyer aux serveurs de collecte de données.
