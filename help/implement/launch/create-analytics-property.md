---
title: Création d’une propriété Analytics dans les balises
description: Créez un espace pour personnaliser la manière dont les données sont collectées à l’aide de balises.
feature: Tags
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/2cZHjGRwvLZPL-jmGLOQpgSXr5Rib8nMeqFWj2cCKAA'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 520
ht-degree: 91%

---

# Création d’une propriété de balise Adobe Analytics

Les balises dans Adobe Experience Platform vous permettent d’intégrer des solutions d’entreprise CX sur votre site web (y compris Analytics). Cette page décrit spécifiquement la manière dont un administrateur de balises peut configurer correctement une implémentation Adobe Analytics de base.

## Conditions préalables

[Créer une suite de rapports](/help/admin/tools/manage-rs/new-rs/t-create-a-report-suite.md) : créez un silo pour les données Analytics à collecter.

## Création d’une propriété de balise et installation d’extensions vitales

Les propriétés sont des conteneurs principaux que vous utilisez pour gérer les balises. Les extensions vous permettent d’installer des balises spécifiques à un produit et de les configurer.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur **[!UICONTROL Nouvelle propriété]**.
1. Donnez un nom à votre propriété, comme le titre de votre site web, et saisissez le domaine sur lequel vous envisagez de mettre en œuvre Analytics. Cliquez sur **[!UICONTROL Enregistrer]**.
1. Cliquez sur la propriété de balise que vous venez de créer pour en saisir les paramètres.
1. Cliquez sur l’onglet **[!UICONTROL Extensions]**, puis sur **[!UICONTROL Catalogue]**.
1. Recherchez « Experience Cloud ID Service », puis cliquez sur **[!UICONTROL Installer]**.
1. Tous les paramètres, y compris l’identifiant de l’organisation CX Enterprise, doivent être déjà renseignés. Cliquez sur **[!UICONTROL Enregistrer]**.
1. Dans le catalogue des extensions, recherchez Adobe Analytics et cliquez sur **[!UICONTROL Installer]**.

Consultez la documentation complète sur l’[extension Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=fr) pour plus d’informations.

## Création d’éléments de données pour Adobe Analytics

Les éléments de données sont des références à des composants spécifiques de votre site pour collecter des valeurs de variable.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise que vous prévoyez d’implémenter sur votre site.
1. Cliquez sur l’onglet **[!UICONTROL Éléments de données]**, puis sur **[!UICONTROL Ajouter un élément de données]**.
1. Définissez les paramètres suivants pour l’élément de données :

   * Nom : nom de la page
   * Extension : Core
   * Type d’élément de données : variable JavaScript
   * Nom de variable JavaScript : `window.document.title`

     >[!NOTE]
     >
     >Cette valeur sert d’exemple pour faciliter le démarrage. Si votre organisation définit une meilleure valeur pour le nom de la page, telle qu’une valeur de couche de données, vous pouvez la saisir ici.
   * Texte clair coché
   * Durée de stockage : aucune
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Création de règles pour Adobe Analytics

Les règles mettent en correspondance les éléments de données avec des valeurs des variables Analytics et déterminent le moment où ces valeurs sont transmises aux serveurs d’Adobe.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise que vous prévoyez d’implémenter sur votre site.
1. Cliquez sur l’onglet **[!UICONTROL Règles]**, puis sur **[!UICONTROL Ajouter une règle]**. Nommez-la `Global Rule`.
1. Cliquez sur **[!UICONTROL Ajouter]** en regard des événements, puis saisissez les paramètres suivants :
   * Extension : Core
   * Type d’événement : bibliothèque chargée (Haut de la page)
   * Nom : Core - Bibliothèque chargée (Haut de la page)
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

## Étapes suivantes

[Déployez votre mise en œuvre d’Analytics dans votre environnement de développement](deploy-dev.md) : obtention de code Analytics fonctionnant dans un environnement de test.
