---
title: Mise en oeuvre d’Adobe Analytics avec des balises dans Adobe Experience Platform
description: Découvrez comment implémenter Adobe Analytics à l’aide de balises
feature: Launch Implementation
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 94%

---

# Mise en oeuvre d’Adobe Analytics avec des balises dans Adobe Experience Platform

Au cours de la durée de vie d’Adobe Analytics, Adobe a proposé plusieurs méthodes différentes pour mettre en œuvre le code sur votre site pour la collecte de données. La méthode actuellement recommandée par Adobe est celle réalisée par le biais de balises dans Adobe Experience Platform.

Les balises dans Adobe Experience Platform représentent une solution de gestion des balises qui vous permet de déployer le code Analytics parallèlement à d’autres exigences de balisage. Adobe propose des intégrations à d’autres solutions et produits et vous permet de déployer du code personnalisé. Toutes ces tâches peuvent être effectuées sans faire appel aux équipes de développement de votre entreprise pour mettre à jour le code de votre site.

Tous les clients disposant d’un contrat Adobe Experience Cloud actif peuvent utiliser les balises. Si vous n’êtes pas sûr d’y avoir accès, contactez l’un des administrateurs système Experience Cloud de votre entreprise.

## Processus global

Pour obtenir une implémentation exécutée à l’aide de balises, procédez comme suit :

1. **Accéder aux balises** : vous pouvez accéder aux balises de Platform par l’intermédiaire d’un administrateur système de votre entreprise.
2. **Créer une propriété de balise** : les propriétés sont des conteneurs globaux utilisés pour référencer les données de la gestion des balises.
3. **Déployez dans un environnement de développement** : vous disposez d’un environnement dans lequel vous pouvez effectuer une itération sur le développement des balises.
4. **Validez et publiez en production** : assurez-vous que tout fonctionne, puis publiez-le en direct.

Pour commencer, consultez la section [Création d’une propriété de balise Analytics](create-analytics-property.md).

## Ressources supplémentaires

Les balises peuvent être hautement personnalisées. Découvrez comment tirer le meilleur parti d’Adobe Analytics en incluant les données appropriées dans votre mise en œuvre.

* [Documentation des balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr#) : découvrez le fonctionnement de l’interface et les extensions disponibles.
* [Extension Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=fr) : utilisez l’extension Analytics pour envoyer des données à Adobe Analytics.
* [Variables de mise en œuvre](../vars/overview.md) : déterminez les variables que vous souhaitez envoyer aux serveurs de collecte de données.
