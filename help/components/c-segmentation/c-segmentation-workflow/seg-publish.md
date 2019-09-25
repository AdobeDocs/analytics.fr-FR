---
description: Permet d’utiliser le segment pour l’activité marketing dans la bibliothèque d’audiences, Target et Audience Manager.
seo-description: Permet d’utiliser le segment pour l’activité marketing dans la bibliothèque d’audiences, Target et Audience Manager.
seo-title: Publication de segments dans Experience Cloud
solution: Analytics
title: Publication de segments dans Experience Cloud
topic: Segments
uuid: e5ce20c0-ce43-423b-a29f-ba66e9e24d27
translation-type: tm+mt
source-git-commit: bac0b1ae330753cfc537817e8da1ea70fbaaf0d5

---


# Publication de segments dans Experience Cloud

>[!IMPORTANT]
>
>Les améliorations de latence concernant la publication de segments et l’interface utilisateur décrites sur cette page ne sont pas encore appliquées à tous les clients. The current production environment is described [here](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html).

Publishing a segment to the Experience Cloud lets you use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], [!DNL Audience Manager], and [!DNL Advertising Cloud]. Recent updates have significantly optimized the publishing workflow. Previously, publishing a usable segment took approximately 48 hours.

Now, processing can take up to 8 hours, but depending on other traffic and on the segment size, processing may be even faster. (However, we currently do not have a way to inform you when the segment is available, so you will have to check manually.) We have also increased the maximum number of publishable segments to 75 (from 20). You can view published segments in Components &gt; Segments.


## Conditions préalables

* Ensure that the report suite that you are saving this segment to is [enabled for the Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). Otherwise you cannot publish it to the Experience Cloud.
* Make sure you are working in a report suite that is mapped to your Experience Cloud organization.[](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)
* Ensure that your organization is using Experience Cloud IDs.
* Before you can publish segments, your Admin needs to assign the Segment Publishing permission to a product profile in the Admin Console, and add you to the product profile.[](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)


## Considérations

* **Report Suite limits: You can publish up to 75 segments per report suite.** This limit is enforced. Si 75 segments sont déjà publiés, vous ne pouvez pas publier d’autres segments tant que vous n’avez pas dépublié suffisamment de segments pour être inférieur au seuil de 75 segments.
* **Limites** d'adhésion : Les audiences partagées avec le groupe [!DNL Experience Cloud] depuis Analytics ne peuvent pas dépasser 20 millions de membres uniques.
* **Data Privacy**: Audiences are not filtered based on the authentication state of a visitor. Si un visiteur peut parcourir votre site qu’il soit authentifié ou non, les actions qui se produisent lorsqu’il n’est pas authentifié peuvent avoir pour conséquence que le visiteur est inclus dans une audience. Review Adobe Experience Cloud privacy to understand the full privacy implications of audience sharing.[](https://www.adobe.com/privacy/experience-cloud.html)
* For a discussion about the differences between segments in  and , go here.**[!DNL Adobe Analytics][!DNL Audience Manager]**[](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)

## Calendrier de publication des segments

| Ce qui est disponible | Lorsqu'il est disponible | Où il est disponible |
|---|---|---|
| Métadonnées (titre et définition du segment) | Immédiatement après la publication | [!DNL Audience Manager], [!UICONTROL Experience Cloud Audience Library], [!DNL Target] |
| Segment utilisable avec abonnement | ~ 8 heures après la publication | Visionneuse de profil du visiteur dans [!DNL Audience Manager] |
| Caractéristique et population membre | Dans les 24 heures | [!DNL Audience Manager] |

## Publication de segments dans le créateur de [!UICONTROL segments]

1. Accédez à **[!UICONTROL Analytics &gt; Espace de travail &gt; Composants &gt; Segments]&gt; +**
1. Créez un segment dans le créateur de [!UICONTROL segments].
1. Fournissez un titre et une description pour le segment ; vous ne pourrez pas l’enregistrer autrement.
1. Check **[!UICONTROL Publish this segment to the Experience Cloud (for *report suite*)]**.
1. Veillez à utiliser "Visiteurs avec un ID d’expérience Cloud" lors de l’affichage des aperçus de segments dans Analytics au lieu de l’aperçu du segment "visiteurs uniques" total lors de la comparaison des nombres Adobe Analytics aux nombres d’Audience Manager.

![](assets/publish-ec.png)

| Élément | Description |
|---|---|
| **[!UICONTROL Publier ce segment dans Experience Cloud (pour *<report suite>*)]** | Lorsque cette option est activée, le titre et la définition du segment (c’est-à-dire l’audience du shell, souvent utilisée dans les plateformes publicitaires) sont partagés instantanément avec Experience Cloud, tandis que l’appartenance au segment est évaluée et partagée toutes les 4 heures. <br> When that audience is associated with an activity in [!DNL Target], for example, [!DNL Analytics] begins sending IDs for visitors that qualify for that Experience Cloud and [!DNL Target] audience. À ce stade, le nom de l’audience et les données correspondantes commencent à s’afficher sur la page Audiences d’Experience Cloud. </br> |
| **[!UICONTROL Fenêtre de création d’audiences]** | La période sélectionnée sert à créer l’audience selon un calendrier variable. Par exemple, "30 derniers jours" (par défaut) inclut les visiteurs qui se sont qualifiés pour l’audience au cours des 30 derniers jours à compter de la date d’aujourd’hui (PAS à partir de la date d’origine de la création du segment). |
| **[!UICONTROL Créer dans la bibliothèque d’audiences]** | Les segments que vous créez et publiez peuvent être rendus disponibles sans latence dans la bibliothèque d’audiences d’Experience Cloud. Elles ne dépendent pas des mises à jour Analytics. Ces segments ne sont pas pris en compte par rapport à votre limite de 75 segments publiés. |
| **[!UICONTROL x sur 75 publié]** | Indique le nombre de segments que vous avez publiés dans Experience Cloud. Cliquez sur le lien pour afficher la liste des segments publiés, ainsi que la suite de rapports et le propriétaire associés. |
| **[!UICONTROL Save]** | Enregistre ce segment. |

## Annulation de la publication ou suppression de segments

Pour supprimer un segment qui a été publié dans Experience Cloud, vous devez tout d’abord en annuler la publication. Pour annuler la publication d’un segment, il vous suffit **de désactiver la case à cocher** que vous avez cochée pour le publier.

>[!NOTE]
>
>Vous **ne pouvez pas** annuler la publication d’un segment qui est actuellement utilisé par l’une des solutions Adobe suivantes : [!DNL Analytics] (dans [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (pour les utilisateurs de [!DNL Core Service] et d’[!DNL Audience Manager]) et tous les autres partenaires externes (pour les utilisateurs de [!DNL Audience Manager]). Vous **pouvez** annuler la publication d’un segment utilisé par [!DNL Target].

## Affichage de l’état de publication des segments dans le Gestionnaire de [!UICONTROL segments]

1. Navigate to Analytics &gt; Components &gt; Segments.
1. Notice the new Published column.  Oui/Non indique si le segment a été publié dans Experience Cloud ou non.

![](assets/publish-status.png)

## Retrieve the  UUID[!DNL Audience Manager]

There are two ways to capture the AAM UUID currently associated with the browser:

* Débogueur Adobe Experience Cloud
* Native developer tool in browsers (e.g., Chrome Developer Tools)

The following screenshots show you how to retrieve the AAM UUID on your browser and use it in Audience Manager Visitor Profile Viewer to validate trait &amp; segment membership.

**Method 1: Use Adobe Experience CLoud Debugger**

1. Download and install Adobe Experience Cloud Debugger in the Chrome Web Store.[](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html)
1. Launch the debugger when loading a page.
1. Scroll to the Audience Manager section and find the AAM UUID set on the current browser page
( in the example below)`50814298273775797762943354787774730612`

![](assets/debugger.jpg)

**Method 2: Use Chrome Developer Tools (or other browser developer tools)**

1. Launch Chrome Developer Tools before loading a page
1. Load the page and check Applications &gt; Cookies. The AAM UUID should be set in the 3rd-party
Demdex cookie (adobe.demdex.net in the example below). [](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html) The field demdex is the AAM UUID set
on the browser ( in the example below).`50814298273775797762943354787774730612`

![Chrome Developer Tools](assets/ggogle-uuid.png)

## Utilisation de la visionneuse de profil du [!UICONTROL visiteur d’Audience Manager]

L’UUID AAM sur le navigateur sera utilisé par défaut lors du chargement de la visionneuse [!UICONTROL de profil du] visiteur. Si vous vérifiez des réalisations de caractéristiques pour d’autres utilisateurs, saisissez un UUID dans le champ UUID, puis cliquez sur [!UICONTROL Actualiser]. Consultez Visionneuse [de profil du](https://marketing.adobe.com/resources/help/en_US/aam/t_visitor_profile_viewer.html) visiteur pour plus d’informations.

![](assets/aam-vpv.png)

## Affichez les caractéristiques du segment dans [!DNL Audience Manager]

Dans AAM, la liste des visiteurs avec des ECID pour un segment donné est évaluée en flux continu, car Analytics partage des segments avec Experience Cloud.

1. Dans [!DNL Audience Manager]Audience Data &gt; Caractéristiques &gt; Caractéristiques Analytics. Un dossier s’affiche pour chaque suite de rapports Analytics associée à votre organisation Experience Cloud. Ces dossiers (pour Caractéristiques, Segments et Sources de données) sont créés lorsque le service principal Profils et audiences/Personnes est lancé ou mis en service.
1. Sélectionnez le dossier de la suite de rapports dans laquelle vous avez créé le segment que vous souhaitez partager [!DNL Audience Manager]. Vous verrez le segment/l’audience que vous avez créé. Lorsque vous partagez un segment, deux choses se produisent dans [!DNL Audience Manager]:
* Une caractéristique est créée, d'abord sans données. Environ. 8 heures après la publication du segment dans [!DNL Analytics], la liste des ECID est intégrée et partagée avec [!DNL Audience Manager] et d’autres solutions Experience Cloud.

![](assets/aam-traits.png)

* Un segment à caractère unique est créé. Il utilise la source de données associée à la suite de rapports dans laquelle vous avez publié le segment.

## Affichez le segment dans [!DNL Adobe Target]

The [!UICONTROL Publish this segment to the Experience Cloud] checkbox during the segment creation process in Adobe Analytics allows the segment to be available within the Adobe Target's custom audience library. Un segment créé dans Analytics ou dans Audience Manager peut être utilisé pour des activités dans Target. Vous pouvez par exemple créer des activités de campagne d’après les mesures de conversion d’Analytics et les segments d’audience créés dans Analytics.
], cliquez sur [!UICONTROL Audiences].
1. On the [!UICONTROL Audiences] page, locate the audience sourced from the [!DNL Experience Cloud]. These audiences are available for use in [!DNL Target] activities.

