---
title: Création d’une propriété Analytics dans les balises
description: Créez un espace pour personnaliser la manière dont les données sont collectées à l’aide de balises.
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 59%

---

# Création d’une propriété de balise Adobe Analytics

Les balises dans Adobe Experience Platform vous permettent d’intégrer des solutions Experience Cloud à votre site web (y compris Analytics). Cette page décrit spécifiquement comment un administrateur de balises peut configurer correctement une mise en oeuvre Adobe Analytics de base.

>[!NOTE]
>Adobe Experience Platform Launch a été rebaptisé en tant que suite de technologies de collecte de données dans Experience Platform. Plusieurs modifications terminologiques ont par conséquent été apportées à la documentation du produit. Reportez-vous au [document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) suivant pour consulter une référence consolidée des modifications terminologiques.

## Conditions préalables

[Création d’une suite de rapports](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md) : création d’un silo pour la collecte des données Analytics..

## Création d’une propriété de balise et installation d’extensions essentielles

Les propriétés sont des conteneurs principaux que vous utilisez pour gérer les balises. Les extensions vous permettent d’installer des balises spécifiques à un produit et de les configurer.

1. Accédez à [experience.adobe.com](https://experience.adobe.com) et connectez-vous lorsque vous y êtes invité.
1. Sélectionnez **[!UICONTROL Lancer / Collecte de données]**.
1. Cliquez sur **[!UICONTROL Aller à Launch / Collecte de données]**, puis sélectionnez **[!UICONTROL Balises]**.
1. Cliquez sur **[!UICONTROL Nouvelle propriété]**.
1. Donnez un nom à votre propriété, comme le titre de votre site web, et saisissez le domaine sur lequel vous envisagez de mettre en œuvre Analytics. Cliquez sur **[!UICONTROL Enregistrer]**.
1. Cliquez sur la propriété de balise que vous venez de créer pour en saisir les paramètres.
1. Cliquez sur l’onglet **[!UICONTROL Extensions]**, puis sur **[!UICONTROL Catalogue]**.
1. Recherchez Service d’identités, puis cliquez sur **[!UICONTROL Installer]**.
1. Tous les paramètres, y compris l’identifiant d’organisation Experience Cloud, doivent être déjà renseignés. Cliquez sur **[!UICONTROL Enregistrer]**.
1. Dans le catalogue des extensions, recherchez Adobe Analytics et cliquez sur **[!UICONTROL Installer]**.

## Création d’éléments de données pour Adobe Analytics

Les éléments de données sont des références à des composants spécifiques de votre site pour collecter des valeurs de variable.

1. Accédez à [experience.adobe.com](https://experience.adobe.com) et connectez-vous lorsque vous y êtes invité.
1. Sélectionnez **[!UICONTROL Lancer / Collecte de données]**.
1. Cliquez sur **[!UICONTROL Aller à Launch / Collecte de données]**, puis sélectionnez **[!UICONTROL Balises]**.
1. Cliquez sur la propriété de balise que vous avez l’intention d’implémenter sur votre site.
1. Cliquez sur l’onglet **[!UICONTROL Éléments de données]**, puis sur **[!UICONTROL Créer un élément de données]**.
1. Définissez les paramètres suivants pour l’élément de données :

   * Nom : nom de la page
   * Extension : Core
   * Type d’élément de données : variable JavaScript
   * Chemin d’accès à la variable : `window.document.title`

      >[!NOTE]
      >
      >Il s’agit d’un exemple de valeur pour faciliter le démarrage. Si votre organisation définit une meilleure valeur pour le nom de la page, telle qu’une valeur de couche de données, vous pouvez la saisir ici.
   * Texte clair coché
   * Durée : Pageview
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Création de règles pour Adobe Analytics

Les règles mettent en correspondance les éléments de données avec des valeurs des variables Analytics et déterminent le moment où ces valeurs sont transmises aux serveurs d’Adobe.

1. Accédez à [experience.adobe.com](https://experience.adobe.com) et connectez-vous lorsque vous y êtes invité.
1. Sélectionnez **[!UICONTROL Lancer / Collecte de données]**.
1. Cliquez sur **[!UICONTROL Aller à Launch / Collecte de données]**, puis sélectionnez **[!UICONTROL Balises]**.
1. Cliquez sur la propriété de balise que vous avez l’intention d’implémenter sur votre site.
1. Cliquez sur **[!UICONTROL Créer une règle]** et nommez-la `Global Rule`.
1. Cliquez sur **[!UICONTROL Ajouter]** en regard des événements, puis saisissez les paramètres suivants :
   * Extension : Core
   * Type d’événement : bibliothèque chargée (Haut de la page)
   * Nom : Core - Bibliothèque chargée (Haut de la page)
   * Commande : 50
1. Cliquez sur **[!UICONTROL Conserver les modifications]**.
1. Sous **[!UICONTROL Actions]**, cliquez sur **[!UICONTROL Ajouter]**, puis saisissez les paramètres suivants :
   * Extension : Adobe Analytics
   * Type d’action : définition de variables
   * Nom de la page : cliquez sur l’icône de conteneur, puis sélectionnez l’élément de données `Page Name`
   * Campagne : paramètre de requête avec une valeur de `cid`
1. Cliquez sur **[!UICONTROL Conserver les modifications]**.
1. Cliquez sur le signe plus en regard des actions pour ajouter une action, puis saisissez les paramètres suivants :
   * Extension : Adobe Analytics
   * Type d’action : envoyer une balise
   * Nom : Adobe Analytics - Envoyer une balise
   * Suivi : s.t()
1. Cliquez sur **[!UICONTROL Conserver les modifications]**.
1. Vérifiez que vous avez défini l’événement et deux actions, puis cliquez sur **[!UICONTROL Enregistrer]**.

## Documentation et ressources supplémentaires

* [Documentation](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=en) de l’extension Adobe Analytics : Documentation complète spécifique à l’extension Adobe Analytics dans les balises .
* [Prise en main des balises](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=en) : Documentation complète pour les balises, y compris un guide de prise en main plus détaillé
* [Canal](https://experienceleague.adobe.com?tag=Launch&amp;lang=fr#recommended/solutions/experience-platform) Adobe Experience Platform Launch : Découvrez comment utiliser des balises par le biais de vidéos

## Étapes suivantes

[Déployez votre mise en œuvre d’Analytics dans votre environnement de développement](deploy-dev.md) : obtention de code Analytics fonctionnant dans un environnement de test.
