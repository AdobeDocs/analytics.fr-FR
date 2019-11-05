---
title: Rapports de conversion dans Adobe Analytics
description: Découvrez comment utiliser les rapports de conversion dans Adobe Analytics.
translation-type: tm+mt
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Rapports de conversion

Une "conversion" est une action effectuée par un visiteur sur votre site qui se traduit directement par les indicateurs clés de votre organisation. Les rapports de conversion affichent des détails sur la conversion des visiteurs.

Cette page suppose que l’utilisateur a une connaissance de base de l’utilisation d’Analysis Workspace. Voir [Création d’un rapport de base dans Analysis Workspace pour les utilisateurs](create-report.md) de Google Analytics si vous ne connaissez pas encore l’outil dans Adobe Analytics.

## Rapports Objectifs

Les objectifs offrent aux utilisateurs de Google Analytics un moyen de définir la conversion d’un site Web. Ils constituent la méthode par défaut pour créer des entonnoirs, inverser le flux comportemental, des entonnoirs multicanaux et l’attribution. Les objectifs dans Google Analytics ne sont pas rétroactifs et ne peuvent être configurés que sur la page d’administration. En outre, elles reposent uniquement sur une page, un événement, le temps passé ou le nombre moyen de pages.

Dans Adobe Analytics, le concept d’un objectif n’est pas nécessaire car les mesures peuvent être appliquées dans n’importe quel contexte. Tant que votre implémentation prend en charge les événements dont vous souhaitez effectuer le suivi, vous pouvez ajuster n’importe quel rapport de conversion et obtenir immédiatement des résultats pour les données historiques.

### Visualisation de l'entonnoir

Le rapport de visualisation de l’entonnoir aide les analystes à se concentrer sur une série particulière d’étapes nécessaires à la conversion. Par exemple, avant d’effectuer un achat, un visiteur sur un site de commerce électronique doit accéder au panier, à la page de facturation et d’expédition, à la page de paiement et à la page de consultation des commandes.

Dans Analysis Workspace, ces données peuvent être visualisées à l’aide de la visualisation Abandons.

1. Cliquez sur l’icône des visualisations sur la gauche, puis faites glisser une visualisation Abandon sur l’espace de travail au-dessus du tableau à structure libre.
2. Cliquez sur l’icône des composants sur la gauche, puis recherchez la dimension **Pages** .
3. Cliquez sur l’icône en forme de flèche en regard de la dimension Pages pour afficher les valeurs de page. Les valeurs de dimension sont colorées en jaune.
4. Localisez la page souhaitée pour agir comme premier point de contact et faites-la glisser dans l’espace intitulé "Ajouter un point de contact" dans la visualisation.
5. Continuez à ajouter des points de contact en faisant glisser les valeurs de page sur la visualisation.

La visualisation Abandons ne se limite pas à la dimension Pages. N’importe quelle dimension, mesure ou segment peut être utilisée pour personnaliser votre rapport d’abandons en fonction des besoins de votre entreprise.

![Visualisation des abandons](/help/technotes/ga-to-aa/assets/fallout.png)

## Rapports eCommerce

Les rapports de commerce électronique sont généralement utilisés par les sites qui vendent des produits ou des services pour mesurer les commandes et les recettes sur les articles achetés. Cette fonctionnalité est disponible dans Adobe Analytics et est connue sous le nom de rapports Produits.

Les rapports de commerce électronique dans Google Analytics et les rapports de produits dans Adobe Analytics nécessitent des modifications d’implémentation personnalisées à utiliser. Pour plus d’informations, voir la dimension [Produits](/help/components/c-variables/dimensionslist/reports-products.md) dans le guide de l’utilisateur Composants.

## Rapports Entonnoir multicanal

Les rapports Entonnoir multicanal fournissent des données de canal marketing supplémentaires au-delà de ce que les rapports d’acquisition fournissent. Ces rapports se concentrent sur le mode de conversion des visiteurs, plutôt que sur le mode d’arrivée des visiteurs sur votre site.

> [!NOTE]
>
> L’utilisation de rapports multicanaux dans Adobe Analytics nécessite à la fois la configuration de canaux marketing et une mise en oeuvre personnalisée pour prendre en compte la variable products et l’événement d’achat. Adobe conseille de travailler avec un consultant en implémentation si ces fonctionnalités ne sont pas encore configurées pour votre suite de rapports.

### Multicanal - Conversions assistées

Les conversions assistées indiquent le nombre de fois où chaque canal a contribué à une conversion. Dans Analysis Workspace, la mesure Aide à la **commande** peut être utilisée.

1. Dans le menu Composants, recherchez la dimension Canal **** marketing et faites-la glisser sur la grande zone de tableau à structure libre intitulée "Déposer une dimension ici".
2. Faites glisser la mesure Aide **** à la commande **au-dessus de l’en-tête de mesure** Occurrencescréée automatiquement pour la remplacer. D’autres mesures peuvent être glissées sur l’espace de travail si vous le souhaitez.

### Multi-canal - Chemins de conversion principaux

Le rapport Chemins de conversion principaux montre les chemins de canal principaux empruntés par un utilisateur avant la conversion. Analysis Workspace utilise un rapport de flux pour visualiser les principaux chemins de conversion.

1. Cliquez sur l’icône Panneaux sur la gauche, puis faites glisser un panneau Attribution au-dessus du tableau à structure libre.
2. Cliquez sur l’icône Composants à gauche, recherchez la dimension Canal **** marketing, puis faites-la glisser dans la zone intitulée "Ajouter une dimension".
3. Recherchez l’événement de conversion souhaité sous Mesures (par exemple, Commandes), puis faites-le glisser dans la zone intitulée "Ajouter une mesure". Notez que les mesures calculées ne sont pas prises en charge pour le panneau Attribution.
4. Cliquez sur Créer.
5. Dans le rapport résultant, recherchez la visualisation "Flux de canal". Ce flux présente les principaux chemins empruntés par un visiteur avant un achat.

Cette visualisation de flux est interactive. Cliquez sur chaque canal pour développer le flux dans l’une ou l’autre direction.

![Visualisation de flux](/help/technotes/ga-to-aa/assets/flow.png)

### Multi-canal - Durée

Le rapport de décalage montre la durée, en jours, de la conversion d’un visiteur sur votre site. Dans Analysis Workspace, ces données sont disponibles à l’aide de la dimension **Jours avant le premier achat** . Elle n’est disponible que dans le contexte d’un événement d’achat correctement implémenté.

1. Dans le menu Composants, recherchez la dimension **Jours avant le premier achat** et faites-la glisser sur la grande zone de tableau à structure libre intitulée "Déposer une dimension ici".
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

Adobe recommande d’utiliser les mesures **Commandes**, **Unités** ou **Recettes** avec cette dimension.

Pour les autres types de conversion, y compris les événements personnalisés, la dimension **Durée avant événement** est disponible. Il indique le temps, en minutes, qu’un visiteur a mis à déclencher l’événement au cours de la visite.

1. Dans le menu Composants, recherchez la dimension **Durée avant événement** et faites-la glisser sur la grande zone de tableau à structure libre intitulée "Déposer une dimension ici".
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Consultez le guide [de traduction des](common-metrics.md) mesures pour plus d’informations sur la manière d’obtenir chaque mesure respective.

Adobe recommande d’utiliser cette dimension avec des événements personnalisés ou des événements d’achat.

### Multi-canal - Longueur de chemin

Le rapport Longueur de chemin montre le nombre de canaux touchés avant un événement de conversion. Dans Analysis Workspace, le panneau Attribution contient ces données dans l’une de ses visualisations.

1. Cliquez sur l’icône Panneaux sur la gauche, puis faites glisser un panneau Attribution au-dessus du tableau à structure libre.
2. Cliquez sur l’icône Composants à gauche, recherchez la dimension Canal **** marketing, puis faites-la glisser dans la zone intitulée "Ajouter une dimension".
3. Recherchez l’événement de conversion souhaité sous Mesures (par exemple, Commandes), puis faites-le glisser dans la zone intitulée "Ajouter une mesure". Notez que les mesures calculées ne sont pas prises en charge pour le panneau Attribution.
4. Cliquez sur Créer.
5. Dans le rapport résultant, recherchez la visualisation Points de contact par voyage. Cet histogramme montre le nombre de canaux qu’un visiteur a touchés avant un achat.
