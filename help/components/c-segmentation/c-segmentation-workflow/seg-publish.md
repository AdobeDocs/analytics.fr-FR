---
description: Permet d’utiliser le segment pour l’activité marketing dans la bibliothèque d’audiences, Target et Audience Manager.
seo-description: Permet d’utiliser le segment pour l’activité marketing dans la bibliothèque d’audiences, Target et Audience Manager.
seo-title: Publication de segments dans Experience Cloud
solution: Analytics
title: Publication de segments dans Experience Cloud
topic: Segments
uuid: e5ce20c0-ce43-423b-a29f-ba66e9e24d27
translation-type: tm+mt
source-git-commit: a900832fa09717295cb45c9dda6d453873641012

---


# Publication de segments dans Experience Cloud

>[!IMPORTANT]
>
>Les améliorations de latence concernant la publication de segments et l’interface utilisateur décrites sur cette page ne sont pas encore appliquées à tous les clients. L’environnement de production actuel est décrit [ici](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html).

Publishing a segment to the Experience Cloud lets you use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], [!DNL Audience Manager], and [!DNL Advertising Cloud]. Les mises à jour récentes ont considérablement optimisé le processus de publication. Auparavant, la publication d’un segment utilisable prenait environ 48 heures.

Désormais, le traitement peut prendre jusqu’à 8 heures, mais en fonction du trafic et de la taille du segment, le traitement peut être encore plus rapide. (Toutefois, nous n’avons pas actuellement le moyen de vous informer lorsque le segment est disponible. Vous devrez donc le vérifier manuellement.) Nous avons également porté le nombre maximum de segments publiables à 75 (contre 20). Vous pouvez afficher les segments publiés dans Composants &gt; Segments.


## Conditions préalables

* Ensure that the report suite that you are saving this segment to is [enabled for the Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). Sinon, vous ne pouvez pas le publier dans Experience Cloud.
* Vérifiez que vous travaillez dans une suite de rapports [mappée à votre organisation](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)Experience Cloud.
* Assurez-vous que votre entreprise utilise des ID Experience Cloud.
* Avant de pouvoir publier des segments, votre administrateur doit affecter l’autorisation Publication [!UICONTROL de] segments à un profil de produit dans la console [d’](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)administration et vous ajouter au profil de produit.


## Considérations

* **Limites** de la suite de rapports : Vous pouvez publier jusqu’à 75 segments par suite de rapports. Cette limite est appliquée. Si 75 segments sont déjà publiés, vous ne pouvez pas publier d’autres segments tant que vous n’avez pas dépublié suffisamment de segments pour être inférieur au seuil de 75 segments.
* **Limites** d'adhésion : Les audiences partagées avec le groupe [!DNL Experience Cloud] depuis Analytics ne peuvent pas dépasser 20 millions de membres uniques.
* **Confidentialité** des données : Les audiences ne sont pas filtrées en fonction de l’état d’authentification d’un visiteur. Si un visiteur peut parcourir votre site qu’il soit authentifié ou non, les actions qui se produisent lorsqu’il n’est pas authentifié peuvent avoir pour conséquence que le visiteur est inclus dans une audience. Examinez la confidentialité [d’](https://www.adobe.com/privacy/experience-cloud.html) Adobe Experience Cloud pour comprendre les implications complètes du partage d’audience sur la confidentialité.
* Pour une discussion sur les **différences entre les segments dans[!DNL Adobe Analytics]et[!DNL Audience Manager]**, allez [ici](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).

## Calendrier de publication des segments

| Ce qui est disponible | Lorsqu'il est disponible | Où il est disponible |
|---|---|---|
| Métadonnées (titre et définition du segment) | Immédiatement après la publication | [!DNL Audience Manager], Bibliothèque [!UICONTROL d’audiences]Experience Cloud, [!DNL Target] |
| Segment utilisable avec abonnement | ~ 8 hours after publishing | Visionneuse de profil du visiteur dans [!DNL Audience Manager] |
| Caractéristique et population membre | Dans les 24 heures | [!DNL Audience Manager] |

## Publication de segments dans le créateur de [!UICONTROL segments]

1. Accédez à **[!UICONTROL Analytics &gt; Espace de travail &gt; Composants &gt; Segments]&gt; +**
1. Créez un segment dans le créateur de [!UICONTROL segments].
1. Fournissez un titre et une description pour le segment ; vous ne pourrez pas l’enregistrer autrement.
1. Check **[!UICONTROL Publish this segment to the Experience Cloud (for *report suite*)]**.

![](assets/publish-ec.png)

>[!IMPORTANT]
>
>Veillez à utiliser "Visiteurs avec un ID d’expérience Cloud" lors de l’affichage des aperçus de segments dans Analytics au lieu de l’aperçu du segment "visiteurs uniques" total lors de la comparaison des nombres d’Adobe Analytics aux nombres d’Audience Manager :
>
>![](assets/seg-vis-ecid.png)

| Élément | Description |
|---|---|
| **[!UICONTROL Publier ce segment dans Experience Cloud (pour *<report suite>*)]** | Lorsque cette option est activée, le titre et la définition du segment (c’est-à-dire l’audience du shell, souvent utilisée dans les plateformes publicitaires) sont partagés instantanément avec Experience Cloud, tandis que l’appartenance au segment est évaluée et partagée toutes les 4 heures. <br> Lorsque cette audience est associée à une activité dans [!DNL Target], par exemple, [!DNL Analytics] commence à envoyer des identifiants pour les visiteurs qui remplissent les conditions requises pour ce cloud d’expérience et [!DNL Target] l’audience. À ce stade, le nom de l’audience et les données correspondantes commencent à s’afficher sur la page Audiences d’Experience Cloud. </br> |
| **[!UICONTROL Fenêtre de création d’audiences]** | La période sélectionnée sert à créer l’audience selon un calendrier variable. Par exemple, "30 derniers jours" (par défaut) inclut les visiteurs qui se sont qualifiés pour l’audience au cours des 30 derniers jours à compter de la date d’aujourd’hui (PAS à partir de la date d’origine de la création du segment). |
| **[!UICONTROL Créer dans la bibliothèque d’audiences]** | Les segments que vous créez et publiez peuvent être rendus disponibles sans latence dans la bibliothèque d’audiences d’Experience Cloud. Elles ne dépendent pas des mises à jour Analytics. Ces segments ne sont pas pris en compte par rapport à votre limite de 75 segments publiés. |
| **[!UICONTROL x sur 75 publié]** | Indique le nombre de segments que vous avez publiés dans Experience Cloud. Cliquez sur le lien pour afficher la liste des segments publiés, ainsi que la suite de rapports et le propriétaire associés. |
| **[!UICONTROL Enregistrer]** | Enregistre ce segment. |

## Annulation de la publication ou suppression de segments

Pour supprimer un segment qui a été publié dans Experience Cloud, vous devez tout d’abord en annuler la publication. Pour annuler la publication d’un segment, il vous suffit **de désactiver la case à cocher** que vous avez cochée pour le publier.

>[!NOTE]
>
>Vous **ne pouvez pas** annuler la publication d’un segment qui est actuellement utilisé par l’une des solutions Adobe suivantes : [!DNL Analytics] (dans [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (pour les utilisateurs de [!DNL Core Service] et d’[!DNL Audience Manager]) et tous les autres partenaires externes (pour les utilisateurs de [!DNL Audience Manager]). Vous **pouvez** annuler la publication d’un segment utilisé par [!DNL Target].

## Affichage de l’état de publication des segments dans le Gestionnaire de [!UICONTROL segments]

1. Accédez à [!UICONTROL Analytics &gt; Composants &gt; Segments].
1. Notez la nouvelle colonne [!UICONTROL Publié] . Oui/Non indique si le segment a été publié dans Experience Cloud ou non.

![](assets/publish-status.png)

## Récupération de l’ [!DNL Audience Manager] UID

Il existe deux manières de capturer l’UUID AAM actuellement associé au navigateur :

* Débogueur Adobe Experience Cloud
* Outil de développement natif dans les navigateurs (par exemple, Outils de développement Chrome)

Les captures d’écran suivantes montrent comment récupérer l’UUID AAM dans votre navigateur et l’utiliser dans la visionneuse de profil du visiteur d’Audience Manager pour valider la caractéristique et l’appartenance à un segment.

**Méthode 1 : Utilisation du débogueur Adobe Experience Cloud**

1. Téléchargez et installez [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) dans Chrome Web Store.
1. Lancez le débogueur lors du chargement d’une page.
1. Scroll to the Audience Manager section and find the AAM UUID set on the current browser page
( in the example below)`50814298273775797762943354787774730612`

![](assets/debugger.jpg)

**Méthode 2 : Utilisation des outils de développement Chrome (ou d’autres outils de développement de navigateur)**

1. Lancement des outils de développement Chrome avant le chargement d’une page
1. Chargez la page et cochez Applications &gt; Cookies. L’UUID AAM doit être défini dans le cookie tiers-partyDemdex ([adobe.demdex.net](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html) dans l’exemple ci-dessous). Le champ demdex est la section UUID AAM du navigateur (`50814298273775797762943354787774730612` dans l’exemple ci-dessous).

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

