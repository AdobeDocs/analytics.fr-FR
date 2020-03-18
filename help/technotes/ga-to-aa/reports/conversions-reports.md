---
title: Rapports de conversion dans Adobe Analytics
description: Découvrez comment utiliser des rapports de conversion dans Adobe Analytics.
translation-type: ht
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Rapports de conversion

Une « conversion » est une action qu’un visiteur effectue sur votre site et qui a un impact direct sur les indicateurs clés de votre organisation. Les rapports de conversion affichent les détails de la conversion des visiteurs.

Cette page part du principe que l’utilisateur maîtrise les bases de l’utilisation d’Analysis Workspace. Voir [Création d’un rapport de base dans Analysis Workspace pour les utilisateurs de Google Analytics](create-report.md) si vous ne connaissez pas encore l’outil dans Adobe Analytics.

## Rapports d’objectifs

Les objectifs offrent aux utilisateurs de Google Analytics un moyen de définir la conversion d’un site web. Il s’agit de la méthode par défaut pour créer des entonnoirs, des flux de comportement inversés, des entonnoirs multicanaux et des attributions. Les objectifs dans Google Analytics ne sont pas rétroactifs et ne peuvent être configurés que sur la page d’administration. De plus, ils sont uniquement basés sur une page, un événement, le temps passé ou le nombre moyen de pages.

Dans Adobe Analytics, le concept d’objectif n’est pas nécessaire, car les mesures peuvent être appliquées dans n’importe quel contexte. Tant que votre mise en œuvre prend en charge les événements dont vous souhaitez effectuer le suivi, vous pouvez ajuster n’importe quel rapport de conversion et obtenir immédiatement les résultats des données historiques.

### Rapport de visualisation entonnoir

Le rapport de visualisation entonnoir aide les analystes à se concentrer sur une série particulière d’étapes nécessaires à la conversion. Par exemple, avant d’effectuer un achat, un visiteur sur un site d’e-commerce doit accéder au panier, à la page de facturation et d’expédition, à la page de paiement et à la page de vérification de la commande.

Dans Analysis Workspace, il est possible de consulter ces données à l’aide de la visualisation des abandons.

1. Cliquez sur l’icône Visualisations à gauche, puis faites glisser une visualisation des abandons sur l’espace de travail situé au-dessus du tableau à structure libre.
2. Cliquez sur l’icône Composants à gauche, puis recherchez la dimension **Pages**.
3. Cliquez sur l’icône en forme de flèche en regard de la dimension pages pour afficher les valeurs de page. Les valeurs de dimension sont en jaune.
4. Localisez la page souhaitée pour agir comme premier point de contact et faites-la glisser sur l’espace « Ajouter un point de contact » dans la visualisation.
5. Continuez à ajouter les points de contact souhaités en faisant glisser les valeurs de page sur la visualisation.

La visualisation d’abandons ne se limite pas à la dimension Pages. N’importe quel(le) dimension, mesure ou segment peut être utilisé(e) pour personnaliser votre rapport d’abandons en fonction des besoins de votre organisation.

![Visualisation des abandons](/help/technotes/ga-to-aa/assets/fallout.png)

## Rapports d’e-commerce

Les rapports d’e-commerce sont généralement utilisés par les sites qui vendent des produits ou des services pour mesurer les commandes et le chiffre d’affaires sur les articles achetés. Cette fonctionnalité, disponible dans Adobe Analytics, est connue sous le nom de Rapports sur les produits.

Des modifications de mise en œuvre personnalisées sont nécessaires pour utiliser les rapports d’e-commerce dans Google Analytics et les rapports de produits dans Adobe Analytics. Pour plus d’informations, voir la dimension [Produits](/help/components/c-variables/dimensionslist/reports-products.md) dans le guide d’utilisation des composants.

## Rapports Entonnoir multicanaux

Les rapports Entonnoir multicanaux fournissent des données de canal marketing supplémentaires à celles des rapports d’acquisition. Ces rapports se concentrent sur la façon dont les visiteurs se convertissent plutôt que sur la façon dont ils arrivent sur votre site.

> [!NOTE]
>
> L’utilisation de rapports multicanaux dans Adobe Analytics nécessite la configuration de canaux marketing et une mise en œuvre personnalisée pour prendre en compte la variable produits et l’événement d’achat. Adobe conseille de travailler avec un consultant en mise en œuvre si ces fonctionnalités ne sont pas encore configurées pour votre suite de rapports.

### Multicanal - Conversions assistées

Les conversions assistées indiquent combien de fois chaque canal a contribué à une conversion. Dans Analysis Workspace, la mesure **Aide à la commande** peut être utilisée.

1. Dans le menu Composants, recherchez la dimension **Canal marketing** et faites-la glisser sur la grande zone de tableau à structure libre « Déposer une dimension ici ».
2. Faites glisser la mesure **Aide à la commande** au-dessus de l’en-tête de la mesure **Occurrences** créée automatiquement pour la remplacer. D’autres mesures peuvent être glissées sur l’espace de travail si vous le souhaitez.

### Multicanal - Chemins de conversion principaux

Le rapport Chemins de conversion principaux montre les principaux chemins d’accès au canal qu’un utilisateur emprunte avant la conversion. Analysis Workspace utilise un rapport de flux pour visualiser les principaux chemins de conversion.

1. Cliquez sur l’icône Panneaux à gauche, puis faites glisser un panneau d’attribution au-dessus du tableau à structure libre.
2. Cliquez sur l’icône Composants à gauche, recherchez la dimension **Canal marketing**, puis faites-la glisser sur la zone « Ajouter une dimension ».
3. Recherchez l’événement de conversion souhaité sous Mesures (par exemple, Commandes), puis faites-le glisser sur la zone « Ajouter une mesure ». Notez que les mesures calculées ne sont pas prises en charge pour le panneau d’attribution.
4. Cliquez sur Créer.
5. Dans le rapport que vous obtenez, recherchez la visualisation « Flux de canal ». Ce flux présente les principaux chemins d’accès qu’un visiteur emprunte avant d’effectuer un achat.

Cette visualisation de flux est interactive. Cliquez sur chaque canal pour développer le flux dans l’une ou l’autre direction.

![Visualisation de flux](/help/technotes/ga-to-aa/assets/flow.png)

### Multicanal - Durée

Le rapport de délai montre la durée, en jours, nécessaire à la conversion d’un visiteur sur votre site. Dans Analysis Workspace, ces données sont disponibles à l’aide de la dimension **Jours avant le premier achat**. Elle n’est disponible que dans le contexte d’un événement d’achat correctement mis en œuvre.

1. Dans le menu Composants, recherchez la dimension **Jours avant le premier achat** et faites-la glisser sur la grande zone de tableau à structure libre « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

Adobe conseille d’utiliser les mesures **Commandes**, **Unités** ou **Recettes** avec cette dimension.

Pour les autres types de conversion, y compris les événements personnalisés, la dimension **Durée avant l’événement** est disponible. Elle indique le temps en minutes qu’un visiteur a mis à déclencher l’événement lors de la visite.

1. Dans le menu Composants, recherchez la dimension **Durée avant l’événement** et faites-la glisser sur la grande zone de tableau à structure libre « Déposer une dimension ici ».
2. Faites glisser les mesures de votre choix sur l’espace de travail à côté de la mesure **Occurrences** créée automatiquement. Pour en savoir plus sur la manière d’obtenir chaque mesure respective, voir le [guide de traduction des mesures](common-metrics.md).

Adobe conseille d’utiliser cette dimension avec des événements personnalisés ou des événements d’achat.

### Multicanal - Longueur de chemin

Le rapport Longueur de chemin montre le nombre de canaux empruntés avant un événement de conversion. Dans Analysis Workspace, le panneau d’attribution contient ces données dans l’une de ses visualisations.

1. Cliquez sur l’icône Panneaux à gauche, puis faites glisser un panneau d’attribution au-dessus du tableau à structure libre.
2. Cliquez sur l’icône Composants à gauche, recherchez la dimension **Canal marketing**, puis faites-la glisser sur la zone « Ajouter une dimension ».
3. Recherchez l’événement de conversion souhaité sous Mesures (par exemple, Commandes), puis faites-le glisser sur la zone « Ajouter une mesure ». Notez que les mesures calculées ne sont pas prises en charge pour le panneau d’attribution.
4. Cliquez sur Créer.
5. Dans le rapport que vous obtenez, recherchez la visualisation « Points de contact par visite ». Cet histogramme montre le nombre de canaux qu’un visiteur emprunte avant d’effectuer un achat.
