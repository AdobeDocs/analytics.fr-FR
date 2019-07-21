---
description: Décrit les étapes que l’administrateur Analytics doit effectuer pour activer la collecte des liens et le téléchargement par les utilisateurs d’Activity Map.
seo-description: Décrit les étapes que l’administrateur Analytics doit effectuer pour activer la collecte des liens et le téléchargement par les utilisateurs d’Activity Map.
seo-title: Activer Carte d'activités
solution: Analytics
title: Activer Carte d'activités
topic: Activity Map
uuid: 30433319-d 0 e 6-4977-951 a -4492 b 356 e 1 f 2
translation-type: tm+mt
source-git-commit: 8f72f8cf086be0eade5616b074123a9f22e33347

---


# Enable Activity Map{#enable-activity-map}

Décrit la procédure à suivre par l’administrateur Analytics pour activer la collecte des liens et le téléchargement par les utilisateurs d’Activity Map.

## Étape 1. Mise à jour de votre code AppMeasurement (Javascript) vers la version 1.6 (ou ultérieure) {#section_5D1586289DF2489289B1B6C1C80C300D}

Le module Activity Map fait partie du fichier AppMeasurement.js (situé en haut du fichier). La bibliothèque AppMeasurement se chargera dans le module Activity Map lorsqu’elle sera instanciée.

Les données d’Activity Map ne peuvent pas être collectées si vous n’effectuez pas la mise à jour vers cette version (ou ultérieure) d’AppMeasurement.

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]** and [implement it](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

   Nous avons inclus un [exemple de code de mise en œuvre](../../../../analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md#concept_EC27DA8A62F5411EBED51284CB7E1734) afin de vous aider à visualiser les changements apportés au code suite à l’intégration du module Activity Map.

1. Validez la mise en œuvre :

   1. Lorsque l’utilisateur clique sur un élément cliquable, les données sont stockées dans un cookie appelé s_sq.
   1. Les données d’Activity Map s’affichent dans la chaîne de requête sur l’appel de suivi. Par exemple :

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Break this report down by **[!UICONTROL Activity Map Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width="400px"}

## Étape 2 : Enable Activity Map reports {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

Vous devez d’abord activer les rapports d’Activity Map au niveau de la suite de rapports.

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Report Suites &gt;[select report suite]&gt; Edit Settings &gt; Activity Map]** &gt; **[!UICONTROL Activity Map Reporting]** .
1. Activity Map collecte les données des liens dans les rapports d’Activity Map. Pour que l’activation fonctionne, vous devez d’abord activer les variables en cliquant sur **[!UICONTROL Activer les rapports d’Activity Map]**.

   Cette étape permet d’ajouter toutes les dimensions Analytics dont vous avez besoin pour collecter des données.

1. Après environ une heure, consultez le [rapport Page d’Activity Map](/help/analyze/activity-map/activitymap-reporting-analytics.md) qui répertorie toutes les pages sur lesquelles les utilisateurs ont cliqué sur un lien.

## Étape 3. Add users to Activity Map access group {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Cliquez sur **[!UICONTROL Ajouter des utilisateurs au groupe]**.

   Vous serez dirigé vers la page de gestion des groupes dans Admin Console.

1. [Ajoutez des utilisateurs à ce groupe](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) et **[!UICONTROL enregistrez le groupe]**.

1. This allow your Admin users to download Activity Map from  **[!UICONTROL Adobe Analytics]** &gt; **[!UICONTROL Tools]** &gt; **[!UICONTROL ActivityMap]** .

<note>
  If you want Non-Admin users to download Activity Map, you need to create a new user group that provides permission to 
 <span class="uicontrol"> Tools </span> &gt; 
 <span class="uicontrol"> Legacy ClickMap Installation </span>. Vous pouvez alors ajouter des utilisateurs non administrateurs à ce groupe. Ce niveau d'autorisation associé à l'accès de Carte d'activités fournit des autorisations complètes pour télécharger et utiliser l'outil. 
</note>
