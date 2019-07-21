---
title: Création d'une propriété Analytics au lancement
seo-title: Création d'une propriété Adobe Analytics dans le lancement d'Adobe Experience Platform
description: Créez un espace pour personnaliser la manière dont les données sont collectées, à l'aide du lancement d'Adobe Experience Platform.
seo-description: Créez un espace pour personnaliser la manière dont les données sont collectées dans Adobe Analytics, à l'aide du lancement d'Adobe Experience Platform.
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Création d'une propriété Analytics dans le lancement d'Adobe Experience Platform

Adobe Experience Platform Launch est l'outil que vous pouvez utiliser pour intégrer les solutions Experience Cloud sur votre site Web (y compris Analytics). Cette page décrit spécifiquement comment un administrateur de lancement peut obtenir une configuration Adobe Analytics de base configurée correctement.

## Conditions préalables

[Création d'une suite de rapports](../../admin/admin-console/create-report-suite.md): Création d'un silo pour que les données Analytics soient collectées

## Création d'une propriété et installation des extensions vitales

Les propriétés sont des conteneurs principaux que vous utilisez pour gérer les balises. Les extensions vous permettent d'installer des balises spécifiques au produit et de les configurer.

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
1. Cliquez sur Nouvelle propriété.
1. Attribuez un nom à votre propriété, comme le titre de votre site Web, et entrez le domaine que vous avez l'intention de mettre en œuvre Analytics. Cliquez sur Enregistrer.
1. Cliquez sur la propriété nouvellement créée pour en saisir les paramètres.
1. Cliquez sur l'onglet Extensions, puis sur Catalogue.
1. Localisez le service d'identité, puis cliquez sur Installer.
1. Tous les paramètres, y compris l'ID d'organisation Experience Cloud, doivent déjà être complétés. Cliquez sur Enregistrer.
1. Dans le catalogue des extensions, recherchez Adobe Analytics et cliquez sur Installer.

## Création d'éléments de données pour Adobe Analytics

Les éléments de données sont des références à des parties spécifiques de votre site pour collecter des valeurs de variable.

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
2. Cliquez sur la propriété Lancer que vous souhaitez implémenter sur votre site.
3. Cliquez sur l'onglet Eléments de données, puis sur Créer un élément de données.
4. Attribuez aux éléments de données les paramètres suivants :
   * Nom : Nom de page
   * Extension : Noyau
   * Type d'élément de données : Variable JavaScript
   * Path to variable: `window.document.title`
      > [!NOTE] Remarque : C'est un exemple de valeur pour vous aider à démarrer. Si votre organisation définit une meilleure valeur pour le nom de la page, telle qu'une valeur de couche de données, vous pouvez la saisir ici.
   * Texte ciblé vérifié
   * Durée : Page vue
5. Cliquez sur Enregistrer.

## Création de règles pour Adobe Analytics

Les règles mappent les éléments de données aux valeurs des variables Analytics et déterminent quand ces valeurs sont envoyées aux serveurs d'Adobe.

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
1. Cliquez sur la propriété Lancer que vous souhaitez implémenter sur votre site.
1. Click Create New Rule and name it `Global Rule`.
1. Cliquez sur Ajouter en regard d'événements, puis saisissez les paramètres suivants :
   * Extension : Noyau
   * Type d'événement : Bibliothèque chargée (Haut de page)
   * Nom : Noyau - Bibliothèque chargée (Haut de page)
   * Commande : 50
1. Cliquez sur Conserver les modifications.
1. Sous Actions, cliquez sur Ajouter, puis saisissez les paramètres suivants :
   * Extension : Adobe Analytics
   * Type d'action : Définition des variables
   * Page Name: click the container icon, and select the `Page Name` data element.
   * Campaign: Query parameter with a value of `cid`
1. Cliquez sur Conserver les modifications.
1. Cliquez sur le signe Plus en regard des actions pour ajouter une autre action, puis saisissez les paramètres suivants :
   * Extension : Adobe Analytics
   * Type d'action : Envoyer balise
   * Nom : Adobe Analytics - Envoyer balise
   * Suivi : s. t ()
1. Cliquez sur Conserver les modifications.
1. Vérifiez que l'événement et deux actions sont définis, puis cliquez sur Enregistrer.

## Documentation et ressources supplémentaires

* [Documentation d'Adobe Analytics](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension): Documentation complète spécifique à l'extension Adobe Analytics dans le lancement d'Adobe Experience Platform.
* [Démarrage avec Launch](https://docs.adobelaunch.com/getting-started): Documentation complète pour Launch, y compris un guide de prise en main plus détaillé
* [Canal YouTube de lancement de Platform Platform](https://www.youtube.com/channel/UCa84ntcvYhPArOBsZIRE2Jw/videos?view=0&shelf_id=0&sort=dd): Apprenez à utiliser Launch via des vidéos

## Étapes suivantes

[Déployez votre implémentation Analytics dans votre environnement de développement](deploy-dev.md): Obtenez le code Analytics dans un environnement de test.
