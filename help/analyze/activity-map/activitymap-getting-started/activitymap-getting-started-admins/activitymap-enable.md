---
description: Décrit la procédure à suivre par l’administrateur Analytics pour activer la collecte des liens et le téléchargement par les utilisateurs d’Activity Map.
title: Activation d’Activity Map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: d4caf0ddc5cf5402bfef94a64db1c00e1c725658
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 74%

---

# Activation d’Activity Map{#enable-activity-map}

Décrit la procédure à suivre par l’administrateur Analytics pour activer la collecte des liens et le téléchargement par les utilisateurs d’Activity Map.

## Étape 1. Mettre à jour votre code de mise en oeuvre {#section_5D1586289DF2489289B1B6C1C80C300D}

Le module Activity Map fait partie du fichier AppMeasurement.js et du SDK Web (version 2.15.0 ou ultérieure).
La bibliothèque AppMeasurement ou le SDK Web chargent le module Activity Map lorsqu’il est instancié.

>[!NOTE]
>
>Les données du Activity Map ne peuvent pas être collectées si vous n’effectuez pas la mise à jour vers **AppMeasurement** **version 1.6** ou supérieur ou **SDK Web** **version 2.15.0** ou supérieur.


1. Téléchargez la dernière bibliothèque JavaScript selon que vous utilisez AppMeasurement ou le SDK Web.

   - **AppMeasurement** code (AppMeasurement_Javascript-1.6.zip) en accédant à  **[!UICONTROL Analytics]** > **[!UICONTROL Administration]** > **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Gestionnaire de code]** et [implémenter](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=fr).

     Nous avons inclus un [exemple de code de mise en œuvre](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md) afin de vous aider à visualiser les changements apportés au code suite à l’intégration du module Activity Map.

   - **SDK Web** code (alloy.js). Voir [Installation du SDK - Option 2 : installation de la version autonome prédéfinie](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=fr#option-2%3A-installing-the-prebuilt-standalone-version) pour plus d’informations. Assurez-vous d’utiliser la version 2.15 ou ultérieure.

     Voir [Suivi des liens](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=fr) pour plus d’informations sur la mise en oeuvre du suivi des liens et sur l’activation du mappage des activités en capturant la variable `region` de l’élément de HTML sur lequel l’utilisateur a cliqué.

     >[!NOTE]
     >
     >L’activation du suivi des liens avec le SDK Web envoie actuellement des événements de lien lorsqu’un client ou une cliente passe d’une page à l’autre. Cela diffère du fonctionnement d’AppMeasurement et peut potentiellement générer des accès facturables supplémentaires envoyés à Adobe.


1. Validez la mise en œuvre :

   1. Lorsque l’utilisateur clique sur un élément cliquable, les données sont stockées dans un cookie appelé s_sq.
   1. Les données d’Activity Map s’affichent dans la chaîne de requête sur l’appel de suivi. Par exemple :

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Ventilez ce rapport par **[!UICONTROL lien d’Activity Map par région]** pour afficher le lien/la région pour cette page :  ![](assets/am_breakdown.png){width="400px"}

## Étape 2. Activation des rapports d’Activity Map {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

Vous devez d’abord activer les rapports d’Activity Map au niveau de la suite de rapports.

1. Connectez-vous à Adobe Analytics et naviguez vers **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > Sélectionner la suite de rapports > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Création de rapports Activity Map]**.
1. Activity Map collecte les données des liens dans les rapports d’Activity Map. Pour que l’activation fonctionne, vous devez d’abord activer les variables en cliquant sur **[!UICONTROL Activer les rapports d’Activity Map]**.

   Cette étape permet d’ajouter toutes les dimensions Analytics dont vous avez besoin pour collecter des données.

1. Après environ une heure, consultez le [rapport Page d’Activity Map](/help/analyze/activity-map/activitymap-reporting-analytics.md) qui répertorie toutes les pages sur lesquelles les utilisateurs ont cliqué sur un lien.

## Étape 3. Ajout d’utilisateurs au groupe d’Activity Map {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Cliquez sur **[!UICONTROL Ajouter des utilisateurs au groupe]**.

   Vous serez dirigé vers la page de gestion des groupes dans Admin Console.

1. [Ajoutez des utilisateurs à ce groupe](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html?lang=fr) et **[!UICONTROL enregistrez le groupe]**.

1. Cela permet à vos utilisateurs de télécharger Activity Map depuis **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Outils]** > **[!UICONTROL Activity Map]**.

>[!NOTE]
>
>Si vous souhaitez que les utilisateurs non-administrateurs téléchargent Activity Map, créez un groupe d’utilisateurs qui accorde l’autorisation d’accès aux « Outils » et à l’« Installation ClickMap héritée ». Ce niveau d’autorisation associé à l’accès à Activity Map permet de télécharger et d’utiliser l’outil.
