---
description: Décrit la procédure à suivre par l’administrateur Analytics pour activer la collecte des liens et le téléchargement par les utilisateurs d’Activity Map.
title: Activation d’Activity Map
feature: Activity Map
role: Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
mini-toc-levels: 3
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 99%

---


# Activer et utiliser Activity Map

Décrit la procédure à suivre par l’administrateur Analytics pour activer la collecte des liens et le téléchargement par les utilisateurs d’Activity Map.

## Étape 1. Activer Activity Map {#update_code}

Le module Activity Map fait partie d’AppMeasurement.js, des balises Adobe Experience Platform et du SDK Web (alloy.js). Les données Activity Map ne peuvent pas être collectées si vous n’effectuez pas la mise à jour vers la **version 2.15.0 du SDK Web** ou les versions ultérieures, ou l’**extension des balises Adobe Analytics v1.90** ou les versions ultérieures, ou la **version 1.6 d’AppMeasurement** ou les versions ultérieures.

+++SDK Web (extension des balises Adobe Experience Platform)

1. Dans les balises Adobe Experience Platform, accédez à la propriété pour laquelle vous implémentez Analytics. Sous [!UICONTROL Extensions] > [!UICONTROL SDK Web Adobe Experience Platform], sélectionnez **[!UICONTROL Activer la collecte de données de clics]** comme indiqué ci-dessous.
1. Créez la bibliothèque avec les modifications.
1. Publiez la bibliothèque en production.

![](assets/web_sdk.png)

**Validation**

Interagissez avec les appels à l’aide de l’onglet Réseau de Developer Console :

1. Chargez le script de développement Launch sur le site.
1. En cas de clic sur les éléments, recherchez « /ee » dans l’onglet Réseau.

   ![](assets/validation1.png)

Adobe Experience Platform Debugger :

1. Téléchargez et installez l’[Adobe Experience Platform Debugger](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob).
1. Accédez à [!UICONTROL Journaux] > [!UICONTROL Edge] > [!UICONTROL Connexion à Edge].

   ![](assets/validation2.jpg)

**Questions fréquentes**

* **L’appel d’interaction ne se déclenche pas dans l’onglet Réseau.**
Collecte de données de clics dans un appel de collecte. Nous devons effectuer un filtrage par « /ee » ou « collect? ».

* **Il n’existe pas d’affichage de payload pour l’appel de collecte.**
L’appel de collecte est conçu de manière à ce que le suivi n’affecte pas la navigation vers d’autres sites. La fonction de déchargement de document s’applique donc aux appels de collecte. Cela n’aura aucun impact sur votre collecte de données, mais si vous devez valider sur la page, ajoutez target = &quot;_blank&quot; à l’élément correspondant. Le lien s’ouvre dans un nouvel onglet.

* **Comment ignorer la collecte de PII ?**
Ajoutez les conditions respectives dans « avant le lien cliquez sur envoyer le rappel » et renvoyez false pour ignorer ces valeurs. [En savoir plus](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=fr)

  Exemple de code :

  ![](assets/sample-code.png)

+++

+++Implémentation manuelle du SDK Web

Voir [Suivi des liens](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=fr) pour plus d’informations sur l’implémentation du suivi des liens et sur l’activation Activity Map en capturant la `region` de l’élément HTML ayant fait l’objet d’un clic.

>[!NOTE]
>
>L’activation du suivi des liens avec le SDK Web envoie actuellement des événements de lien lorsqu’un client ou une cliente passe d’une page à l’autre. Cela diffère du fonctionnement d’AppMeasurement et peut potentiellement générer des accès facturables supplémentaires envoyés à Adobe.

+++

+++Extension Analytics (balises Adobe Experience Platform)

Dans les balises Adobe Experience Platform, accédez à la propriété pour laquelle vous implémentez Analytics. Dans la boîte de dialogue [!UICONTROL Installer l’extension], sélectionnez **[!UICONTROL Utiliser Activity Map]**.

![](assets/aa_extension.png)

+++

+++AppMeasurement

1. Téléchargez la dernière bibliothèque JavaScript pour AppMeasurement.
Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Administration]** > **[!UICONTROL Tous les administrateurs et administratrices]** > **[!UICONTROL Personne gestionnaire de code]**.
1. Implémentez-la en suivant [ces instructions](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=fr).

+++

## Étape 2. Activation des rapports d’Activity Map {#enable}

Vous devez d’abord activer les rapports Activity Map au niveau de la suite de rapports.

1. Connectez-vous à Adobe Analytics et naviguez vers **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > Sélectionner la suite de rapports > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Création de rapports Activity Map]**.

1. Activity Map collecte les données des liens dans les rapports d’Activity Map. Pour que l’activation fonctionne, vous devez d’abord activer les variables en cliquant sur **[!UICONTROL Activer les rapports d’Activity Map]**.

   Cette étape permet d’ajouter toutes les dimensions Analytics dont vous avez besoin pour collecter des données.

   ![](assets/enable.png)

1. Après environ une heure, consultez le [rapport Page d’Activity Map](/help/analyze/activity-map/activitymap-reporting-analytics.md) qui répertorie toutes les pages sur lesquelles les utilisateurs ont cliqué sur un lien.

## Étape 3. Ajouter des utilisateurs et utilisatrices au profil de produit [!UICONTROL Accès à Activity Map] {#add_users}

1. Cliquez sur **[!UICONTROL Ajouter des utilisateurs et utilisatrices au groupe]**.

   Cela vous redirige vers la page de profil de produit dans [Adobe Admin Console](https://adminconsole.adobe.com/E2F05B3B52F54D2E0A490D44@AdobeOrg/overview).

1. Si vous n’avez pas créé un profil de produit [!UICONTROL Accès à Activity Map], faites-le maintenant. Les éléments d’autorisation requis pour ce profil sont les suivants : [!UICONTROL Outils Analytics] > [!UICONTROL Activity Map] et [!UICONTROL Outils Analytics] > [!UICONTROL Publication de segments].

1. Ajoutez des utilisateurs et utilisatrices à ce profil de produit. Cela permet à vos utilisateurs et utilisatrices de télécharger Activity Map depuis **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Outils]** > **[!UICONTROL Activity Map]**.

