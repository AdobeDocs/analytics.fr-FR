---
description: Vous permet d'utiliser le segment pour une activité marketing dans la bibliothèque d'audiences, Target et Audience Manager.
seo-description: Vous permet d'utiliser le segment pour une activité marketing dans la bibliothèque d'audiences, Target et Audience Manager.
seo-title: Publication de segments dans Experience Cloud
solution: Analytics
title: Publication de segments dans Experience Cloud
topic: Segments
uuid: e 5 ce 20 c 0-ce 43-423 b-a 29 f-ba 66 e 9 e 24 d 27
translation-type: tm+mt
source-git-commit: 6298c00cf4c74a493b6ba6266763d693897d5299

---


# Publication de segments dans Experience Cloud

>[!IMPORTANT]
>
>Les améliorations de latence concernant la publication de segments et l'interface utilisateur décrite sur cette page ne sont pas encore déployées sur tous les clients. The current production environment is described [here](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html).

Publishing a segment to the Experience Cloud lets you use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], [!DNL Audience Manager], and [!DNL Advertising Cloud]. Les dernières mises à jour ont considérablement optimisé le processus de publication. Auparavant, la publication d'un segment utilisable prenait environ 48 heures.

Désormais, le traitement peut prendre jusqu'à 8 heures, mais en fonction du trafic et de la taille du segment, le traitement peut être encore plus rapide. (Cependant, nous n'avons pas actuellement la possibilité de vous informer lorsque le segment est disponible. Vous devez donc vérifier manuellement). Nous avons également augmenté le nombre maximal de segments publiables à 75 (à partir de 20). Vous pouvez afficher les segments publiés dans Composants &gt; Segments.


## Conditions préalables

* Ensure that the report suite that you are saving this segment to is [enabled for the Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). Sinon, vous ne pouvez pas la publier dans Experience Cloud.
* Make sure you are working in a report suite that is [mapped to your Experience Cloud organization](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).
* Before you can publish segments, your Admin needs to assign the [!UICONTROL Segment Publishing] permission to a product profile in the [Admin Console](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html), and add you to the product profile.


## Considérations

* **Limites de suite de rapports**: Vous pouvez publier jusqu'à 75 segments par suite de rapports. Cette limite est appliquée. Si 75 segments sont déjà publiés, vous ne pouvez pas publier de segments supplémentaires tant que vous ne publiez pas suffisamment de segments pour obtenir un seuil inférieur à 75 segments.
* **Limites d'adhésion**: Les audiences partagées à [!DNL Experience Cloud] partir d'Analytics ne peuvent pas dépasser 20 millions de membres uniques.
* **Confidentialité des données**: Les audiences ne sont pas filtrées en fonction de l'état d'authentification d'un visiteur. Si un visiteur peut parcourir votre site qu’il soit authentifié ou non, les actions qui se produisent lorsqu’il n’est pas authentifié peuvent avoir pour conséquence que le visiteur est inclus dans une audience. Review [Adobe Experience Cloud privacy](https://www.adobe.com/privacy/experience-cloud.html) to understand the full privacy implications of audience sharing.
* For a discussion about the differences between segments in [!DNL Adobe Analytics] and [!DNL Audience Manager], go [here](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).

## Calendrier de publication de segment

| Ce qui est disponible | Lorsqu'elle est disponible | Où elle est disponible |
|---|---|---|
| Meta - données (titre et définition de segment) | Immédiatement après la publication | [!DNL Audience Manager], [!UICONTROL bibliothèque d'audiences Experience Cloud], [!DNL Target] |
| Segment utilisable avec adhésion | ~ 8 heures après la publication | Visitor Profile Viewer in [!DNL Audience Manager] |
| Population de caractéristiques et d'adhérents | Dans les 24 heures | [!DNL Audience Manager] |

## Publish segments in [!UICONTROL Segment Builder]

1. Navigate to [!UICONTROL Analytics &gt; Workspace &gt; Components &gt; Segments] &gt; +
1. Create a segment in the [!UICONTROL Segment Builder].
1. Fournissez un titre et une description du segment ; vous ne pourrez pas l'enregistrer autrement.
1. Check [!UICONTROL Publish this segment to the Experience Cloud (for *report suite*)].

![](assets/publish-ec.png)

| Élément | Description |
|---|---|
| Publier ce segment dans Experience Cloud (pour `<report suite>`) | Lorsque cette option est activée, le titre et la définition du segment (c'est-à-dire le public shell souvent utilisé dans les plateformes publicitaires) sont partagés instantanément avec Experience Cloud, tandis que l'appartenance au segment est évaluée et partagée toutes les 4 heures. <br> Lorsqu'une audience est associée à une activité dans [!DNL Target], par exemple, [!DNL Analytics] commence à envoyer des identifiants pour les visiteurs qui remplissent les critères de cette expérience et [!DNL Target] du public. À ce stade, le nom de l’audience et les données correspondantes commencent à s’afficher sur la page Audiences d’Experience Cloud. </br> |
| Fenêtre de création d’audiences | La période que vous sélectionnez est utilisée pour créer l'audience par calendrier variable. Par exemple, « 30 derniers jours » (par défaut) inclut les visiteurs qui ont qualifié l'audience au cours des 30 derniers jours à compter de la date d'aujourd'hui (SAUF à partir de la date d'origine où le segment a été créé). |
| Créer dans la bibliothèque d’audiences | Les segments que vous créez et publiez peuvent être disponibles sans latence dans la bibliothèque d'audiences Experience Cloud. Elles ne dépendent pas des mises à jour Analytics. Ces segments ne sont pas comptabilisés par rapport à la limite de 75 segments publiés. |
| x of 75 Published | Affiche le nombre de segments que vous avez publiés dans Experience Cloud. Cliquez sur le lien pour afficher la liste des segments publiés et leur suite et leur propriétaire associés. |
| Enregistrer | Enregistre ce segment. |

## Annulation de la publication ou suppression de segments

Pour supprimer un segment qui a été publié dans Experience Cloud, vous devez d'abord le dépublier. To unpublish a segment, just **unclick** the checkbox that you used to publish it.

>[!NOTE]
>
>You **cannot** unpublish a segment that is currently in use by any of the following Adobe solutions: [!DNL Analytics] (in [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (for [!DNL Core Service] &amp; [!DNL Audience Manager] customers) and all other external partners (for [!DNL Audience Manager] customers). You **can** unpublish a segment that is in use by [!DNL Target].

## View segment publishing status in the [!UICONTROL Segment Manager]

1. Navigate to [!UICONTROL Analytics &gt; Components &gt; Segments].
1. Notice the new [!UICONTROL Published] column. Oui/Non indique si le segment a été publié dans Experience Cloud ou non.

![](assets/publish-status.png)

## Retrieve the [!DNL Audience Manager] UUID

Il existe deux méthodes pour capturer l'UUID AAM actuellement associé au navigateur :

* Débogueur Adobe Experience Cloud
* Outil de développement natif dans les navigateurs (par exemple, Chrome Developer Tools)

Les captures d'écran suivantes montrent comment récupérer l'UUID AAM sur votre navigateur et l'utiliser dans la visionneuse de profils du visiteur Audience Manager pour valider l'appartenance à la caractéristique et au segment.

**Méthode 1 : Utiliser le débogueur d'Adobe Experieence CLoud**

1. Download and install [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) in the Chrome Web Store.
1. Lancez le débogueur lors du chargement d'une page.
1. Scroll to the Audience Manager section and find the AAM UUID set on the current browser page
(`50814298273775797762943354787774730612` in the example below)

![](assets/debugger.jpg)

**Méthode 2 : Utiliser Chrome Developer Tools (ou d'autres outils de développement de navigateur)**

1. Lancer Chrome Developer Tools avant de charger une page
1. Chargez la page et vérifiez Applications &gt; Cookies. The AAM UUID should be set in the 3rd-party
Demdex cookie ([adobe.demdex.net](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html) in the example below). The field demdex is the AAM UUID set
on the browser (`50814298273775797762943354787774730612` in the example below).

![Chrome Developer Tools](assets/ggogle-uuid.png)

## Use Audience Manager [!UICONTROL Visitor Profile Viewer]

The AAM UUID on the browser will be used by default when [!UICONTROL Visitor Profile Viewer] is loaded. If verifying trait realizations for other users, input a UUID in the UUID field and click [!UICONTROL Refresh]. Refer to [Visitor Profile Viewer](https://marketing.adobe.com/resources/help/en_US/aam/t_visitor_profile_viewer.html) for more information.

![](assets/aam-vpv.png)

## View the segment traits in [!DNL Audience Manager]

Dans AAM, la liste des visiteurs avec des ecid pour un segment donné est évaluée de la manière dont Analytics partage les segments avec Experience Cloud.

1. In [!DNL Audience Manager], go to [!UICONTROL Audience Data &gt; Traits &gt; Analytics Traits]. Un dossier s'affiche pour chaque suite de rapports Analytics associée à votre organisation Experience Cloud. Ces dossiers (pour Caractéristiques, Segments et Sources de données) sont créés lorsque le service principal Profils et audiences/Personnes est initié ou configuré.
1. Select the folder for the report suite in which you previously created the segment you wanted to share with [!DNL Audience Manager]. Le segment/public que vous avez créé s'affiche. When you share a segment, 2 things happen in [!DNL Audience Manager]:
* Une caractéristique est créée, d'abord sans données. Approbateur. 8 hours after the segment gets published in [!DNL Analytics], the list of ECIDs gets onboarded and shared with [!DNL Audience Manager] and other Experience Cloud solutions.

![](assets/aam-traits.png)

* Un segment à caractéristique unique est créé. Elle utilise la source de données associée à la suite de rapports dans laquelle vous avez publié le segment.

## View the segment in [!DNL Adobe Target]

The [!UICONTROL Publish this segment to the Experience Cloud] checkbox during the segment creation process in Adobe Analytics allows the segment to be available within the Adobe Target's custom audience library. Un segment créé dans Analytics ou dans Audience Manager peut être utilisé pour des activités dans Target. Vous pouvez par exemple créer des activités de campagne d’après les mesures de conversion d’Analytics et les segments d’audience créés dans Analytics.
], click [!UICONTROL Audiences].
1. On the [!UICONTROL Audiences] page, locate the audience sourced from the [!DNL Experience Cloud]. These audiences are available for use in [!DNL Target] activities.
