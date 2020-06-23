---
title: Création d’une propriété Analytics dans Launch
description: Créez un espace pour personnaliser la manière dont les données sont collectées à l’aide d’Adobe Experience Platform Launch.
translation-type: ht
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# Création d’une propriété Analytics dans Adobe Experience Platform Launch

Adobe Experience Platform Launch est l’outil que vous pouvez utiliser pour intégrer des solutions Experience Cloud à votre site web (y compris Analytics). Cette page décrit spécifiquement la manière dont un administrateur Launch peut configurer correctement une mise en œuvre Adobe Analytics de base.

## Conditions préalables

[Création d’une suite de rapports](/help/admin/admin-console/create-report-suite.md) : création d’un silo pour la collecte des données Analytics.

## Création d’une propriété et installation d’extensions vitales

Les propriétés sont des conteneurs principaux que vous utilisez pour gérer les balises. Les extensions vous permettent d’installer des balises spécifiques à un produit et de les configurer.

1. Accédez à [launch.adobe.com](https://launch.adobe.com) et connectez-vous si vous y êtes invité.
1. Cliquez sur « Nouvelle propriété ».
1. Donnez un nom à votre propriété, comme le titre de votre site web, et saisissez le domaine sur lequel vous envisagez de mettre en œuvre Analytics. Cliquez sur Enregistrer.
1. Cliquez sur la propriété que vous venez de créer pour en saisir les paramètres.
1. Cliquez sur l’onglet Extensions, puis sur Catalogue.
1. Recherchez Service d’identité, puis cliquez sur Installer.
1. Tous les paramètres, y compris l’identifiant d’organisation Experience Cloud, doivent être déjà renseignés. Cliquez sur Enregistrer.
1. Dans le catalogue des extensions, recherchez Adobe Analytics et cliquez sur Installer.

## Création d’éléments de données pour Adobe Analytics

Les éléments de données sont des références à des composants spécifiques de votre site pour collecter des valeurs de variable.

1. Accédez à [launch.adobe.com](https://launch.adobe.com) et connectez-vous si vous y êtes invité.
2. Cliquez sur la propriété Launch que vous prévoyez de mettre en œuvre sur votre site.
3. Cliquez sur l’onglet Eléments de données, puis sur Créer un élément de données.
4. Définissez les paramètres suivants pour l’élément de données :
   * Nom : nom de la page
   * Extension : Core
   * Type d’élément de données : variable JavaScript
   * Chemin d’accès à la variable : `window.document.title`
      > [!NOTE] Remarque : il s’agit d’un exemple de valeur pour faciliter le démarrage. Si votre organisation définit une meilleure valeur pour le nom de la page, telle qu’une valeur de couche de données, vous pouvez la saisir ici.
   * Texte clair coché
   * Durée : Pageview
5. Cliquez sur Enregistrer.

## Création de règles pour Adobe Analytics

Les règles mettent en correspondance les éléments de données avec des valeurs des variables Analytics et déterminent le moment où ces valeurs sont transmises aux serveurs d’Adobe.

1. Accédez à [launch.adobe.com](https://launch.adobe.com) et connectez-vous si vous y êtes invité.
1. Cliquez sur la propriété Launch que vous prévoyez de mettre en œuvre sur votre site.
1. Cliquez sur Créer une règle et nommez-la `Global Rule`.
1. Cliquez sur Ajouter en regard des événements, puis saisissez les paramètres suivants :
   * Extension : Core
   * Type d’événement : bibliothèque chargée (Haut de la page)
   * Nom : Core - Bibliothèque chargée (Haut de la page)
   * Commande : 50
1. Cliquez sur Conserver les modifications.
1. Sous Actions, cliquez sur Ajouter, puis saisissez les paramètres suivants :
   * Extension : Adobe Analytics
   * Type d’action : définition de variables
   * Nom de la page : cliquez sur l’icône de conteneur, puis sélectionnez l’élément de données `Page Name`
   * Campagne : paramètre de requête avec une valeur de `cid`
1. Cliquez sur Conserver les modifications.
1. Cliquez sur le signe plus en regard des actions pour ajouter une action, puis saisissez les paramètres suivants :
   * Extension : Adobe Analytics
   * Type d’action : envoyer une balise
   * Nom : Adobe Analytics - Envoyer une balise
   * Suivi : s.t()
1. Cliquez sur Conserver les modifications.
1. Vérifiez que vous avez défini l’événement et deux actions, puis cliquez sur Enregistrer.

## Documentation et ressources supplémentaires

* [Documentation sur l’extension Adobe Analytics](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension) : documentation complète spécifique à l’extension Adobe Analytics dans Adobe Experience Platform Launch.
* [Prise en main de Launch](https://docs.adobelaunch.com/getting-started) : documentation complète pour Launch, y compris un guide de prise en main plus détaillé.
* [Chaîne YouTube Adobe Experience Platform Launch](https://www.youtube.com/channel/UCa84ntcvYhPArOBsZIRE2Jw/videos?view=0&amp;shelf_id=0&amp;sort=dd) : découvrez comment utiliser Launch par le biais de vidéos.

## Étapes suivantes

[Déployez votre mise en œuvre d’Analytics dans votre environnement de développement](deploy-dev.md) : obtention de code Analytics fonctionnant dans un environnement de test.
