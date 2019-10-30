---
description: Explique les étapes que l’administrateur Analytics doit effectuer pour activer la collecte des liens [!DNL Activity Map] et le téléchargement des utilisateurs.
seo-description: Explique les étapes que l’administrateur Analytics doit effectuer pour activer la collecte des liens [!DNL Activity Map] et le téléchargement des utilisateurs.
seo-title: Activer [!Carte d’activités DNL]
solution: Analytics
title: Activer [!Carte d’activités DNL]
topic: Activity Map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# Activer [!DNL Activity Map]{#enable-activity-map}

Explains the steps the Analytics Admin needs to complete to enable [!DNL Activity Map] link collection and user download.

## Étape 1. Mise à jour de votre code AppMeasurement (Javascript) vers la version 1.6 (ou ultérieure) {#section_5D1586289DF2489289B1B6C1C80C300D}

The [!DNL Activity Map] module is part of the AppMeasurement.js file (located at the top of the file). The AppMeasurement library will load the [!DNL Activity Map] module when instantiated.

[!DNL Activity Map] les données ne peuvent pas être collectées, sauf si vous effectuez une mise à jour vers cette version (ou version ultérieure) d’AppMeasurement.

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]** and [implement it](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

   Nous avons inclus un [exemple de code de mise en œuvre](../../../../analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md#concept_EC27DA8A62F5411EBED51284CB7E1734) afin de vous aider à visualiser les changements apportés au code suite à l’intégration du module [!DNL Activity Map]

1. Validez la mise en œuvre:

   1. Lorsque l’utilisateur clique sur un élément cliquable, les données sont stockées dans un cookie appelé s_sq.
   1. The [!DNL Activity Map] data can be seen in the query-string on the tracking call. Par exemple :

      ```
      …&c.&a.&[!DNL Activity Map].&link=My%20Link&region=My%20Region&page=My%20Page&.[!DNL Activity Map]&.a&.c&...
      ```

1. Break this report down by **[!UICONTROL [!DNL Activity Map]Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width="400px"}

## Étape 2 : Activer les [!DNL Activity Map] rapports {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

First, you need to enable [!DNL Activity Map] reports at a report-suite level.

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Report Suites &gt;[select report suite]&gt; Edit Settings &gt;[!DNL Activity Map]]** &gt; **[!UICONTROL [!DNL Activity Map]Reporting]** .
1. [!DNL Activity Map] collecte les données de lien dans [!DNL Activity Map] les rapports. For the activation to happen, you must first activate the variables by clicking **[!UICONTROL Enable[!DNL Activity Map]Reports]**.

   Cette étape permet d’ajouter toutes les dimensions Analytics dont vous avez besoin pour collecter des données.

1. After about an hour, check the [[!DNL Activity Map] Page report](/help/analyze/activity-map/activitymap-reporting-analytics.md), which shows all the pages where users clicked on a link.

## Étape 3. Ajouter des utilisateurs au groupe [!DNL Activity Map] d’accès {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Cliquez sur **[!UICONTROL Ajouter des utilisateurs au groupe]**.

   Vous serez dirigé vers la page de gestion des groupes dans Admin Console.

1. [Ajoutez des utilisateurs à ce groupe](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) et **[!UICONTROL enregistrez le groupe]**.

1. This allow your Admin users to download [!DNL Activity Map] from  **[!UICONTROL Adobe Analytics]** &gt; **[!UICONTROL Tools]** &gt; **[!UICONTROL ActivityMap]** .

<note>
  Si vous souhaitez que les utilisateurs non-administrateurs téléchargent [!Carte d’activités DNL], vous devez créer un nouveau groupe d’utilisateurs qui autorise <span class="uicontrol"> Outils </span> &gt; <span class="uicontrol"> Installation héritée de ClickMap </span>. Vous pouvez ensuite ajouter des utilisateurs non administrateurs à ce groupe. Ce niveau d’autorisation associé à l’accès à la Carte d’activités [!DNL] fournira des autorisations complètes pour télécharger et utiliser l’outil. 
</note>
