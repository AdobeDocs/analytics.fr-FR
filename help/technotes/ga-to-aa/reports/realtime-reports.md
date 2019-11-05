---
title: Rapports en temps réel dans Adobe Analytics
description: Découvrez comment extraire des rapports en temps réel dans Adobe Analytics, destinés aux utilisateurs plus familiers avec Google Analytics.
translation-type: tm+mt
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Rapports en temps réel

Les rapports en temps réel montrent ce qui se passe sur votre site en ce moment. Ces types de rapports sont particulièrement utiles pour voir les résultats immédiats des mises à jour apportées à votre site. Par exemple, une entreprise qui réalise une vente le vendredi noir peut évaluer le trafic sur des pages spécifiques et déterminer les ventes à classer par priorité en fonction des performances de ce moment.

![Rapport en temps réel](/help/technotes/ga-to-aa/assets/realtime.png)

Les rapports en temps réel sont l’une des rares fonctionnalités qui n’ont pas encore été introduites dans Analysis Workspace. Utilisez les rapports et analyses pour obtenir ces données. Ils nécessitent une configuration simple pour commencer à collecter des données.

Pour accéder à la page de configuration des rapports en temps réel (autorisations d’administrateur requises) :

1. Cliquez sur [!UICONTROL Rapports] dans la navigation de l’en-tête d’Adobe Analytics.
2. Dans le menu de gauche, cliquez sur Mesures *[!UICONTROL du]* site &gt; *[!UICONTROL Temps]* réel.
3. Si la suite de rapports n’est pas encore activée en temps réel, un message s’affiche avec un lien pour configurer la suite de rapports. Si la suite de rapports est activée en temps réel, cliquez sur [!UICONTROL Configurer] près du titre du rapport en temps réel.

Adobe permet à trois rapports en temps réel de collecter des données simultanément. Chacun doit être configuré avant de commencer à collecter des données en temps réel.

![Configuration des rapports en temps réel](/help/technotes/ga-to-aa/assets/realtime_config.png)

## Emplacements en temps réel

Les emplacements en temps réel vous indiquent où résident les visiteurs qui visitent votre site au moment présent. Pour configurer l’un de vos trois rapports en temps réel afin d’afficher les données d’emplacement :

1. Cliquez sur [!UICONTROL Configurer] près du titre du rapport en temps réel.
2. Sous l’un des emplacements de rapport en temps réel :
   * Nommez votre rapport en temps réel ; par exemple, "Emplacements".
   * Les instances sont généralement utilisées comme mesure. Pour le moment, les utilisateurs/visiteurs uniques ne sont pas disponibles dans les rapports en temps réel.
   * Pour la dimension principale, le pays de géosegmentation est généralement utilisé. GeoSegmentation Region, GeoSegmentation US DMA et GeoSegmentation City sont également disponibles.
   * Pour les deux dimensions secondaires, utilisez les données supplémentaires souhaitées pour ce trafic. Les dimensions secondaires ne doivent pas nécessairement être spécifiques à l’emplacement.
3. Click [!UICONTROL Save and View Report].

## Sources de trafic en temps réel

Les sources de trafic en temps réel vous indiquent d’où proviennent les visiteurs qui visitent votre site au moment présent. Pour configurer l’un de vos trois rapports en temps réel afin d’afficher les données de sources de trafic :

1. Cliquez sur "Configurer" près du titre du rapport en temps réel.
2. Sous l’un des emplacements de rapport en temps réel :
   * Nommez votre rapport en temps réel ; par exemple, "Sources de trafic".
   * Les instances sont généralement utilisées comme mesure. Pour le moment, les utilisateurs/visiteurs uniques ne sont pas disponibles dans les rapports en temps réel.
   * Pour la dimension principale, le domaine référent est généralement utilisé. Moteur de recherche et Mot-clé de recherche sont également disponibles.
   * Pour les deux dimensions secondaires, utilisez les données supplémentaires souhaitées pour ce trafic. Les dimensions secondaires ne doivent pas nécessairement être spécifiques aux sources de trafic.
3. Click [!UICONTROL Save and View Report].

## Contenu en temps réel

Le contenu en temps réel vous indique les pages actuellement consultées par vos visiteurs. Pour configurer l’un de vos trois rapports en temps réel afin d’afficher les données de contenu :

1. Cliquez sur [!UICONTROL Configurer] près du titre du rapport en temps réel.
2. Sous l’un des emplacements de rapport en temps réel :
   * Nommez votre rapport en temps réel ; par exemple, "Contenu".
   * Les instances sont généralement utilisées comme mesure. Pour le moment, les utilisateurs/visiteurs uniques ne sont pas disponibles dans les rapports en temps réel.
   * Pour la dimension principale, la page est généralement utilisée. La section du site et le serveur sont également disponibles si votre implémentation définit ces variables.
   * Pour les deux dimensions secondaires, utilisez les données supplémentaires souhaitées pour ce trafic. Les dimensions secondaires ne doivent pas nécessairement être spécifiques au contenu.
3. Click [!UICONTROL Save and View Report].

## Evénements en temps réel

Les événements en temps réel vous indiquent les événements qui se produisent le plus sur votre site. Dans Google Analytics, un événement capture le nombre de fois où une action spécifique (généralement une action sans rapport avec une page vue) s’est produite. Les événements GA sont envoyés avec une catégorie, une étiquette et une action. Dans Adobe Analytics, les événements personnalisés sont des mesures auxquelles sont attribués des noms conviviaux dans la console d’administration et qui peuvent être analysés en même temps que n’importe quelle dimension. Si vous recherchez dans Adobe Analytics une dimension similaire aux événements Google Analytics, appliquez la dimension Lien personnalisé, souvent utilisée comme fourre-tout pour la collecte de données qui n’ont aucun rapport avec les pages vues (en plus des liens de sortie - pour les sorties - et des liens de téléchargement - pour les téléchargements).

> [!NOTE] Lors de l’utilisation d’événements personnalisés dans des rapports en temps réel, la valeur de dimension doit être définie dans le même accès que l’événement personnalisé. Par exemple, si vous consultez un événement personnalisé "Inscriptions" pour la dimension "Domaine référent", aucune donnée ne sera renvoyée sans implémentation supplémentaire. Le domaine référent n’apparaissant que sur le premier accès et un événement personnalisé s’affichant généralement plus tard dans la visite, les données ne peuvent pas être associées dans les rapports en temps réel. Ces données sont disponibles à l’aide d’Analysis Workspace à l’aide de la latence de traitement standard, qui est généralement de 30 à 90 minutes.

## Conversions en temps réel

Les conversions en temps réel présentent les données différemment selon les plateformes. Dans Google Analytics, les objectifs ressemblent aux mesures et aux événements de réussite dans Adobe Analytics. Vous pouvez utiliser la plupart des mesures dans Adobe Analytics (à la fois des mesures personnalisées comme des événements de réussite et des mesures standard comme des recettes) dans les rapports Temps réel. Tout comme Google Analytics, vous pouvez également appliquer des dimensions telles que le nom du produit, le code de suivi et les performances des campagnes dans les rapports en temps réel.

1. Cliquez sur [!UICONTROL Configurer] près du titre du rapport en temps réel.
2. Sous l’un des emplacements de rapport en temps réel :
   * Nommez votre rapport en temps réel ; par exemple, "Conversions".
   * Les instances sont généralement utilisées comme mesure. Pour le moment, les utilisateurs/visiteurs uniques ne sont pas disponibles dans les rapports en temps réel.
   * Pour la dimension principale, le code de suivi est généralement utilisé. La dimension Produits est également disponible si votre implémentation l’utilise.
   * Pour les deux dimensions secondaires, utilisez les données supplémentaires souhaitées pour ce trafic. Les dimensions secondaires ne doivent pas nécessairement être spécifiques aux conversions.
3. Click [!UICONTROL Save and View Report].

> [!NOTE] Si vous utilisez des événements en dehors des instances, tels que les commandes, assurez-vous que votre implémentation définit la dimension et l’événement sur le même accès. Si les dimensions et les événements ne se déclenchent pas sur le même accès, ces données sont disponibles dans Analysis Workspace à l’aide de la latence de traitement standard, qui est généralement de 30 à 90 minutes.
