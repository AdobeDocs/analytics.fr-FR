---
description: Décrit la procédure à suivre par l’administrateur Analytics pour activer la collecte des liens et le téléchargement par les utilisateurs d’Activity Map.
title: Activation d’Activity Map
topic: Activity map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Activation d’Activity Map {#enable-activity-map}

Décrit la procédure à suivre par l’administrateur Analytics pour activer la collecte des liens et le téléchargement par les utilisateurs d’Activity Map.

## Étape 1. Mise à jour de votre code AppMeasurement (Javascript) vers la version 1.6 (ou ultérieure) {#section_5D1586289DF2489289B1B6C1C80C300D}

Le module Carte  de fait partie du fichier AppMeasurement.js (situé en haut du fichier). La bibliothèque AppMeasurement chargera le module  Map  lorsqu’elle sera instanciée.

 données de carte  ne peuvent pas être collectées, sauf si vous effectuez une mise à jour vers cette version (ou version ultérieure) d’AppMeasurement.

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Code Manager]** and [implement it](https://marketing.adobe.com/resources/help/fr_FR/sc/implement/js_implementation.html).

   Nous avons inclus quelques [exemples de code](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md) de mise en oeuvre afin de vous aider à visualiser les modifications apportées au code en incluant le module  de carte  du.

1. Validez la mise en œuvre :

   1. Lorsqu’un utilisateur clique sur un élément cliquable, les données sont stockées dans un cookie nommé s_sq.
   1. Les données de  de carte de  sont visibles dans la chaîne de  sur l’appel de suivi. Par exemple :

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Break this report down by **[!UICONTROL Activity Map Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width=&quot;400px&quot;}

## Étape 2 : Activation des rapports d’Activity Map {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

Vous devez d’abord activer les rapports d’Activity Map au niveau de la suite de rapports.

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites >[select report suite]> Edit Settings > Activity Map]** > **[!UICONTROL Activity Map Reporting]** .
1. Activity Map collecte les données des liens dans les rapports d’Activity Map. For the activation to happen, you must first activate the variables by clicking **[!UICONTROL Enable Activity Map Reports]**.

   Cette étape permet d’ajouter toutes les dimensions Analytics dont vous avez besoin pour collecter des données.

1. Au bout d’environ une heure, consultez le rapport [](/help/analyze/activity-map/activitymap-reporting-analytics.md)de la page de  du qui présente toutes les pages sur lesquelles les utilisateurs ont cliqué sur un lien.

## Étape 3. Ajout d’utilisateurs au groupe d’Activity Map {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Cliquez sur **[!UICONTROL Add Users to Group]**.

   Vous serez dirigé vers la page de gestion des groupes dans Admin Console.

1. [Ajouter les utilisateurs à ce groupe](https://marketing.adobe.com/resources/help/fr_FR/reference/groups.html) et **[!UICONTROL Save Group]**.

1. This allow your Admin users to download Activity Map from  **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL ActivityMap]** .

>[!NOTE] Si vous souhaitez que les utilisateurs non-administrateurs téléchargent Activity Map, créez un groupe d’utilisateurs qui accorde l’autorisation d’accès aux outils et à l’installation ClickMap héritée. Ce niveau d’autorisation associé à l’accès à Activity Map permet de télécharger et d’utiliser l’outil.
