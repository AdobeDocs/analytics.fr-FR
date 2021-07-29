---
title: Mise en oeuvre avec des balises dans Adobe Experience Platform
description: Découvrez comment mettre en oeuvre Adobe Analytics à l’aide de balises
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 47%

---

# Mise en oeuvre avec des balises dans Adobe Experience Platform

>[!NOTE]
>Adobe Experience Platform Launch a été rebaptisé en tant que suite de technologies de collecte de données dans Experience Platform. Plusieurs modifications terminologiques ont par conséquent été apportées à la documentation du produit. Reportez-vous au [document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) suivant pour consulter une référence consolidée des modifications terminologiques.

Au cours de la durée de vie d’Adobe Analytics, Adobe a proposé plusieurs méthodes différentes pour mettre en œuvre le code sur votre site pour la collecte de données. La méthode actuellement recommandée par l’Adobe consiste à utiliser des balises dans Adobe Experience Platform.

Dans Adobe Experience Platform, les balises sont une solution de gestion des balises qui vous permet de déployer du code Analytics parallèlement à d’autres exigences de balisage. Adobe propose des intégrations à d’autres solutions et produits et vous permet de déployer du code personnalisé. Toutes ces tâches peuvent être effectuées sans faire appel aux équipes de développement de votre entreprise pour mettre à jour le code de votre site.

Tous les clients disposant d’un principal contrat Adobe Experience Cloud peuvent utiliser des balises. Si vous n’êtes pas sûr d’y avoir accès, contactez l’un des administrateurs système Experience Cloud de votre entreprise.

## Processus global

Pour obtenir une mise en oeuvre s’exécutant à l’aide de balises, procédez comme suit :

1. **Accédez aux balises** : Vous pouvez accéder aux balises Platform par l’intermédiaire d’un administrateur système de votre entreprise.
2. **Créez une propriété** de balise : Les propriétés sont des conteneurs globaux utilisés pour référencer les données de la gestion des balises.
3. **Déployez dans un environnement de développement** : vous disposez d’un environnement dans lequel vous pouvez effectuer une itération sur le développement des balises.
4. **Validez et publiez en production** : assurez-vous que tout fonctionne, puis publiez-le en direct.

Voir [Création d’une propriété de balise Analytics](create-analytics-property.md) pour commencer.

## Ressources supplémentaires

Les balises peuvent être hautement personnalisées. Découvrez comment tirer le meilleur parti d’Adobe Analytics en incluant les données appropriées dans votre mise en œuvre.

* [Documentation](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en#) sur les balises : Découvrez le fonctionnement de l’interface et les extensions disponibles.
* [Extension Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=en) : utilisez l’extension Analytics pour envoyer des données à Adobe Analytics.
* [Variables de mise en œuvre](../vars/overview.md) : déterminez les variables que vous souhaitez envoyer aux serveurs de collecte de données.
