---
title: Présentation de la mise en oeuvre avec le lancement
description: Découvrez comment implémenter Adobe Analytics à l’aide d’Adobe Experience Platform Launch
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Présentation de la mise en oeuvre avec le lancement

Au cours de la durée de vie d’Adobe Analytics, Adobe a proposé plusieurs méthodes différentes pour implémenter le code sur votre site pour la collecte de données. La méthode actuellement recommandée par Adobe est le lancement d’Adobe Experience Platform.

Launch est une solution de gestion des balises qui vous permet de déployer le code Analytics parallèlement à d’autres exigences de balisage. Adobe propose des intégrations à d’autres solutions et produits et vous permet de déployer du code personnalisé. Toutes ces tâches peuvent être effectuées sans compter sur les équipes de développement de votre entreprise pour mettre à jour le code de votre site.

Tous les clients disposant d’un contrat Adobe Experience Cloud actif peuvent utiliser Launch. Si vous n’êtes pas sûr d’y avoir accès, contactez l’un des administrateurs système Experience Cloud de votre entreprise.

## Flux global

Pour obtenir une mise en oeuvre exécutée à l’aide de Launch, procédez comme suit :

1. **Accédez au lancement**: Vous pouvez accéder à Lancer par l’intermédiaire d’un administrateur système de votre entreprise.
2. **Créez une propriété**: Les propriétés sont des conteneurs globaux utilisés pour référencer les données de la gestion des balises.
3. **Déployer dans un environnement** de développement : Vous disposez d’un environnement dans lequel vous pouvez effectuer une itération sur le développement des balises.
4. **Valider et publier en production**: Assurez-vous que tout fonctionne, puis publiez-le en direct.

Voir [Création d’une propriété Analytics dans Adobe Experience Platform Launch](create-analytics-property.md) pour commencer.

## Ressources supplémentaires

Le lancement peut être hautement personnalisé. Découvrez comment tirer le meilleur parti d’Adobe Analytics en incluant les données appropriées dans votre implémentation.

* [Documentation](https://docs.adobe.com/content/help/en/launch/using/overview.html)du lancement : Découvrez le fonctionnement de l’interface et les extensions disponibles.
* [Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html)Adobe Analytics : Utilisez l’extension Analytics pour envoyer des données à Adobe Analytics.
* [Variables](../vars/overview.md)d’implémentation : Déterminez les variables que vous souhaitez envoyer aux serveurs de collecte de données.
