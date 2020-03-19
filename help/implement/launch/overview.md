---
title: Présentation de la mise en œuvre avec Launch
description: Découvrez comment mettre en œuvre Adobe Analytics à l’aide d’Adobe Experience Platform Launch
translation-type: ht
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Présentation de la mise en œuvre avec Launch

Au cours de la durée de vie d’Adobe Analytics, Adobe a proposé plusieurs méthodes différentes pour mettre en œuvre le code sur votre site pour la collecte de données. La méthode actuellement recommandée par Adobe est Adobe Experience Platform Launch.

Launch est une solution de gestion des balises qui vous permet de déployer le code Analytics parallèlement à d’autres exigences de balisage. Adobe propose des intégrations à d’autres solutions et produits et vous permet de déployer du code personnalisé. Toutes ces tâches peuvent être effectuées sans faire appel aux équipes de développement de votre entreprise pour mettre à jour le code de votre site.

Tous les clients disposant d’un contrat Adobe Experience Cloud actif peuvent utiliser Launch. Si vous n’êtes pas sûr d’y avoir accès, contactez l’un des administrateurs système Experience Cloud de votre entreprise.

## Processus global

Pour obtenir une mise en œuvre exécutée à l’aide de Launch, procédez comme suit :

1. **Accédez à Launch** : vous pouvez accéder à Launch par l’intermédiaire d’un administrateur système de votre entreprise.
2. **Créez une propriété** : les propriétés sont des conteneurs globaux utilisés pour référencer les données de la gestion des balises.
3. **Déployez dans un environnement de développement** : vous disposez d’un environnement dans lequel vous pouvez effectuer une itération sur le développement des balises.
4. **Validez et publiez en production** : assurez-vous que tout fonctionne, puis publiez-le en direct.

Voir [Création d’une propriété Analytics dans Adobe Experience Platform Launch](create-analytics-property.md) pour commencer.

## Ressources supplémentaires

Launch peut être hautement personnalisé. Découvrez comment tirer le meilleur parti d’Adobe Analytics en incluant les données appropriées dans votre mise en œuvre.

* [Documentation du Launch](https://docs.adobe.com/content/help/fr-FR/launch/using/overview.html) : découvrez le fonctionnement de l’interface et les extensions disponibles.
* [Extension Adobe Analytics](https://docs.adobe.com/content/help/fr-FR/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html) : utilisez l’extension Analytics pour envoyer des données à Adobe Analytics.
* [Variables de mise en œuvre](../vars/overview.md) : déterminez les variables que vous souhaitez envoyer aux serveurs de collecte de données.
