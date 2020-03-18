---
title: Rapports en temps réel dans Adobe Analytics
description: Découvrez comment extraire, dans Adobe Analytics, des rapports en temps réel destinés aux utilisateurs plus habitués à Google Analytics.
translation-type: ht
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Rapports en temps réel

Les rapports en temps réel montrent ce qui se passe sur votre site actuellement. Ces types de rapports sont très utiles pour voir les résultats immédiats des mises à jour apportées à votre site. Par exemple, une entreprise effectuant une opération de ventes pour le Black Friday peut évaluer le trafic sur des pages spécifiques et déterminer les ventes prioritaires en fonction des performances à cette époque.

![Rapport en temps réel](/help/technotes/ga-to-aa/assets/realtime.png)

Les rapports en temps réel comptent parmi les rares fonctionnalités n’ayant pas encore été introduites dans Analysis Workspace. Utilisez Reports &amp; Analytics pour obtenir ces données. Quelques opérations simples de configuration sont nécessaires pour commencer à collecter des données.

Pour accéder à la page de configuration des rapports en temps réel (droits d’administrateur requis) :

1. Cliquez sur [!UICONTROL Rapports] dans la navigation de l’en-tête d’Adobe Analytics.
2. Dans le menu de gauche, cliquez sur *[!UICONTROL Mesures du site]* > *[!UICONTROL Temps réel]*.
3. Si la suite de rapports n’est pas encore activée en temps réel, un message contenant un lien pour configurer la suite de rapports s’affiche. Si la suite de rapports est activée en temps réel, cliquez sur [!UICONTROL Configurer] près du titre du rapport en temps réel.

Adobe permet la collecte simultanée de données par trois rapports en temps réel. Chacun doit être configuré avant de commencer à collecter des données en temps réel.

![Configuration des rapports en temps réel](/help/technotes/ga-to-aa/assets/realtime_config.png)

## Emplacements en temps réel

Les emplacements en temps réel vous indiquent où résident les visiteurs présents sur votre site actuellement. Pour configurer l’un de vos trois rapports en temps réel afin d’afficher les données d’emplacement :

1. Cliquez sur [!UICONTROL Configurer] près du titre du rapport en temps réel.
2. Sous l’un des emplacements de rapport en temps réel :
   * Nommez votre rapport en temps réel, par exemple « Emplacements ».
   * Les instances sont généralement utilisées comme mesure. Pour l’instant, les utilisateurs/visiteurs uniques ne sont pas disponibles dans les rapports en temps réel.
   * Géosegmentation - Pays est généralement utilisé comme dimension principale. GeoSegmentation - Région, GeoSegmentation - DMA É.U. et GeoSegmentation - Ville sont également disponibles.
   * Pour les deux dimensions secondaires, utilisez les données supplémentaires de prédilection pour ce trafic. Les dimensions secondaires n’ont pas à être spécifiques de l’emplacement.
3. Cliquez sur [!UICONTROL Enregistrer et afficher le rapport].

## Sources de trafic en temps réel

Les sources de trafic en temps réel vous indiquent d’où viennent les visiteurs présents sur votre site actuellement. Pour configurer l’un de vos trois rapports en temps réel afin d’afficher les données de sources de trafic :

1. Cliquez sur « Configurer » près du titre du rapport en temps réel.
2. Sous l’un des emplacements de rapport en temps réel :
   * Nommez votre rapport en temps réel, par exemple « Sources de trafic ».
   * Les instances sont généralement utilisées comme mesure. Pour l’instant, les utilisateurs/visiteurs uniques ne sont pas disponibles dans les rapports en temps réel.
   * Le domaine référent est généralement utilisé comme dimension principale. Moteur de recherche et Mot-clé de recherche sont également disponibles.
   * Pour les deux dimensions secondaires, utilisez les données supplémentaires de prédilection pour ce trafic. Les dimensions secondaires n’ont pas à être spécifiques aux sources de trafic.
3. Cliquez sur [!UICONTROL Enregistrer et afficher le rapport].

## Contenu en temps réel

Le contenu en temps réel vous indique les pages que vos visiteurs consultent actuellement. Pour configurer l’un de vos trois rapports en temps réel afin d’afficher les données de contenu :

1. Cliquez sur [!UICONTROL Configurer] près du titre du rapport en temps réel.
2. Sous l’un des emplacements de rapport en temps réel :
   * Nommez votre rapport en temps réel, par exemple « Contenu ».
   * Les instances sont généralement utilisées comme mesure. Pour l’instant, les utilisateurs/visiteurs uniques ne sont pas disponibles dans les rapports en temps réel.
   * Page est généralement utilisée comme dimension principale. Section du site et Serveur sont également disponibles si votre mise en œuvre définit ces variables.
   * Pour les deux dimensions secondaires, utilisez les données supplémentaires de prédilection pour ce trafic. Les dimensions secondaires n’ont pas à être spécifiques au contenu.
3. Cliquez sur [!UICONTROL Enregistrer et afficher le rapport].

## Événements en temps réel

Les événements en temps réel vous indiquent quels événements se produisent le plus sur votre site. Dans Google Analytics, un événement capture le nombre de fois qu’une action spécifique (généralement une action sans rapport avec une page vue) s’est produite. Les événements GA sont envoyés avec une catégorie, un libellé et une action. Dans Adobe Analytics, les événements personnalisés sont des mesures auxquelles sont attribués des noms conviviaux dans l’Admin Console et qui peuvent être analysés en même temps que n’importe quelle dimension. Dans Adobe Analytics, si vous recherchez une dimension similaire aux événements Google Analytics, appliquez la dimension Lien personnalisé, souvent utilisée comme fourre-tout pour collecter les données sans lien avec les pages vues (en plus des liens de sortie, pour les sorties, et des liens de téléchargement, pour les téléchargements).

> [!NOTE] En cas d’utilisation d’événements personnalisés dans des rapports en temps réel, la valeur de dimension doit être définie dans le même accès que l’événement personnalisé. Par exemple, si vous affichez un événement personnalisé « Enregistrement » pour la dimension « Domaine référent », aucune donnée ne sera renvoyée sans mise en œuvre supplémentaire. Étant donné que le domaine référent n’apparaît que lors du premier accès et qu’un événement personnalisé s’affiche généralement plus tard dans la visite, les données ne peuvent pas être associées à des rapports en temps réel. Ces données peuvent être consultées à dans Analysis Workspace en utilisant une latence de traitement standard, généralement comprise entre 30 et 90 minutes.

## Conversions en temps réel

Les conversions en temps réel présentent les données différemment selon les plateformes. Les objectifs dans Google Analytics ressemblent aux mesures et aux événements de succès dans Adobe Analytics. Dans Adobe Analytics, vous pouvez utiliser la plupart des mesures (aussi bien des mesures personnalisées comme des événements de succès que des mesures standard comme le chiffre d’affaires) dans les rapports en temps réel. Comme dans Google Analytics, vous pouvez appliquer des dimensions telles que le nom du produit, le code de suivi et les performances des campagnes dans les rapports en temps réel.

1. Cliquez sur [!UICONTROL Configurer] près du titre du rapport en temps réel.
2. Sous l’un des emplacements de rapport en temps réel :
   * Nommez votre rapport en temps réel, par exemple « Conversions ».
   * Les instances sont généralement utilisées comme mesure. Pour l’instant, les utilisateurs/visiteurs uniques ne sont pas disponibles dans les rapports en temps réel.
   * Code de suivi est généralement utilisé comme dimension principale. La dimension Produits est aussi disponible si votre mise en œuvre l’utilise.
   * Pour les deux dimensions secondaires, utilisez les données supplémentaires de prédilection pour ce trafic. Les dimensions secondaires n’ont pas à être spécifiques aux conversions.
3. Cliquez sur [!UICONTROL Enregistrer et afficher le rapport].

> [!NOTE] Si vous utilisez des événements en dehors des instances telles que Commandes, assurez-vous que votre mise en œuvre définit la dimension et l’événement sur le même accès. Si les dimensions et les événements ne se déclenchent pas sur le même accès, ces données peuvent être consultées dans Analysis Workspace en utilisant une latence de traitement standard, généralement comprise entre 30 et 90 minutes.
