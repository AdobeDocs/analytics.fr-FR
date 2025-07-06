---
description: Découvrez comment publier des segments pour l’activité marketing dans la bibliothèque d’audiences, Target et Audience Manager.
title: Publier les segments
feature: Segmentation
exl-id: 0215f896-d3f8-42cc-ac8d-8a94b009927b
source-git-commit: c44bffa45ab8ed29ea28b91b2b3dc51811ab25fe
workflow-type: tm+mt
source-wordcount: '1332'
ht-degree: 45%

---

# Publier des segments {#publish-segments}

>[!CONTEXTUALHELP]
>id="components_segments_publishing"
>title="Publication Experience Cloud"
>abstract="Vous pouvez publier l’audience dans la bibliothèque d’audiences, où elle peut être utilisée pour des activités marketing dans Target et d’autres solutions Experience Cloud."

>[!CONTEXTUALHELP]
>id="components_segments_audiencelibrary"
>title="Bibliothèque d’audiences"
>abstract="Les segments créés dans la bibliothèque d’audiences sont disponibles instantanément et ne dépendent pas des mises à jour d’Analytics."


Vous pouvez publier un segment Adobe Analytics dans Experience Cloud. Vous pouvez donc utiliser le segment pour l’activité marketing dans [!DNL Audience Manager] et dans d’autres canaux d’activation, notamment [!DNL Advertising Cloud], [!DNL Target] et [!DNL Campaign].

Vous pouvez publier des segments Analytics sur Experience Cloud en moins de 8 heures. Utilisez ces segments pour activer des audiences dans Audience Manager vers toutes les destinations en aval.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Publication de segments](https://video.tv.adobe.com/v/32842?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Adobe Campaign (Classic et Standard) se comporte différemment dans le sens où il génère une latence supplémentaire de 24 heures en plus de la latence de 8 heures.

## Conditions préalables

* Assurez-vous que la suite de rapports dans laquelle vous enregistrez ce segment est [activée pour Experience Cloud](https://experienceleague.adobe.com/en/docs/analytics/components/segmentation/segmentation-workflow/seg-publish). Dans le cas contraire, vous ne pouvez pas le publier dans Experience Cloud.
* Assurez-vous que votre entreprise utilise des Experience Cloud ID.
* Avant de pouvoir publier des segments, votre administrateur doit affecter l’autorisation [!UICONTROL Publication de segments] à un profil de produit dans l’[Admin Console](https://experienceleague.adobe.com/en/docs/core-services/interface/administration/admin-tool-experience-cloud) et vous ajouter au profil de produit.

## Considérations

* **Limites de suites de rapports** : vous pouvez publier jusqu’à 75 segments par suite de rapports. Cette limite est appliquée. Si 75 segments ont déjà été publiés, vous ne pouvez pas en publier d’autres tant que vous n’avez pas annulé la publication de suffisamment de segments pour arriver sous le seuil de 75 segments.
* **Limites d’abonnements** : les audiences partagées avec [!DNL Experience Cloud] depuis Adobe Analytics ne doivent pas dépasser 20 millions de membres uniques.
* **Confidentialité des données** : les audiences ne sont pas filtrées d’après l’état d’authentification d’un visiteur. Un visiteur peut être en mesure de parcourir votre site dans des états non authentifiés et authentifiés. Les actions qui se produisent lorsqu’un visiteur n’est pas authentifié peuvent toujours entraîner l’inclusion d’un visiteur dans une audience. Examinez la [politique de confidentialité d’Adobe Experience Cloud](https://www.adobe.com/fr/privacy/experience-cloud.html) pour bien comprendre toutes les implications du partage des audiences en matière de confidentialité.
* Pour plus d’informations sur les **différences entre les segments dans [!DNL Adobe Analytics] et[!DNL Audience Manager]**, voir [Présentation des segments dans Analytics et Audience Manager](https://experienceleague.adobe.com/en/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments).

## Journal de publication des segments

| Ce qui est disponible | Lorsqu’il est disponible | Où il est disponible |
|---|---|---|
| Métadonnées (titre et définition du segment) | Immédiatement après la publication | [!DNL Audience Manager], [!UICONTROL Bibliothèque d’audiences Experience Cloud], [!DNL Target] |
| Segment utilisable avec abonnement | Jusqu’à huit heures après la publication | Visionneuse du profil du visiteur dans [!DNL Audience Manager] |
| Caractéristique et population membre | Dans les 24 à 48 heures | [!DNL Audience Manager] |

>[!NOTE]
>Une fois par semaine, toutes les données sont entièrement synchronisées pour prendre en compte les deltas ou les incohérences non capturés au cours de la semaine précédente.

## Publication de segments dans [!UICONTROL Créateur de segments]

1. Dans Adobe Analytics, accédez à **[!UICONTROL Composants]** > **[!UICONTROL Segments]**
1. Sélectionnez **[!UICONTROL Ajouter]** pour créer un segment.
   ![Publier Experience Cloud](assets/publish-ec.png)
1. Fournissez un titre et une description pour le segment. Ces champs sont obligatoires avant de pouvoir enregistrer le segment.
1. Dans la section **[!UICONTROL Publication Experience Cloud]**, sélectionnez l’option **[!UICONTROL Publier ce segment dans Experience Cloud (pour *suite de rapports*)]**.

   >[!IMPORTANT]
   >
   >Veillez à surveiller les **[!UICONTROL Visiteurs avec un Experience Cloud ID]** dans l’**[!UICONTROL Aperçu des données]** au lieu des **[!UICONTROL Visiteurs uniques]** lorsque vous comparez des nombres Adobe Analytics aux nombres Audience Manager.
   >

| Élément | Description |
|---|---|
| **[!UICONTROL Publier ce segment dans Experience Cloud (par *suite de rapports*)]** | Lorsque cette option est activée, le titre et la définition du segment sont partagés instantanément avec Experience Cloud, tandis que l’appartenance au segment est évaluée et partagée toutes les 4 heures. <br> Lorsque cette audience est associée à une activité dans [!DNL Target], par exemple, [!DNL Analytics] commence à envoyer les identifiants des visiteurs à inclure dans cette audience Experience Cloud et [!DNL Target]. À ce stade, le nom de l’audience et les données correspondantes commencent à s’afficher sur la page [!DNL Audience Library] dans Experience Cloud. </br> |
| **[!UICONTROL Fenêtre de création d’audiences]** | La période que vous sélectionnez est utilisée pour créer l’audience sur une base de calendrier glissant. Par exemple, la mention **[!UICONTROL 30 derniers jours]** (par défaut) inclut les visiteurs qui se sont qualifiés pour l’audience au cours des 30 derniers jours à compter de la date d’aujourd’hui (et NON à compter de la date d’origine de création du segment). |
| **[!UICONTROL Créer dans la bibliothèque d’audiences]** | Les segments que vous créez et publiez peuvent être disponibles sans latence sur la page [!DNL Audience Library] d’Experience Cloud. Ils ne dépendent pas des mises à jour Analytics. Ces segments ne sont pas pris en compte par rapport à votre limite de 75 segments publiés. |
| **[!UICONTROL x sur 75 publiés]** | Nombre de segments que vous avez publiés sur Experience Cloud. Cliquez sur le lien pour afficher la liste des segments publiés, ainsi que la suite de rapports et le propriétaire qui y sont associés. |
| **[!UICONTROL Enregistrer]** | Enregistre ce segment. |

## Dépublier ou supprimer des segments

>[!CAUTION]
>
>Pour supprimer un segment qui a été publié dans Experience Cloud, vous devez d’abord dépublier le segment. Pour dépublier un segment, désélectionnez simplement **[!UICONTROL Publier ce segment dans Experience Cloud (par *suite de rapports*)]**.


>[!NOTE]
>
>Vous **ne pouvez pas** dépublier un segment qui est actuellement utilisé par l’une des solutions Adobe suivantes : [!DNL Analytics] (dans [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (pour les utilisateurs de [!DNL Core Service] et d’[!DNL Audience Manager]) et tous les autres partenaires externes (pour les utilisateurs de [!DNL Audience Manager]). Vous **pouvez** dépublier un segment utilisé par [!DNL Target].

## Affichage du statut de publication des segments

Le nombre maximal de segments Adobe Analytics pouvant être publiés est de 75.

Pour afficher les segments publiés :

1. Dans Adobe Analytics, accédez à **[!UICONTROL Composants]** > **[!UICONTROL Segments]**.

1. Affichez la colonne **[!UICONTROL Publié]**. **[!UICONTROL Oui]** dans cette colonne indique que le segment est publié dans Experience Cloud. **[!UICONTROL Non]** indique que le segment n’est pas publié.

## Récupérer l’[!DNL Audience Manager]UUID

Il existe deux manières de capturer l’UUID Adobe Audience Manager actuellement associé au navigateur :

* Adobe Experience Cloud Debugger
* Outil de développement natif dans les navigateurs (par exemple, outils de développement Chrome)

Les captures d’écran suivantes vous montrent comment récupérer l’UUID Adobe Audience Manager dans votre navigateur et l’utiliser dans la visionneuse de profil du visiteur Audience Manager pour valider l’appartenance à une caractéristique et à un segment.

### Méthode 1 : utiliser Adobe Experience Cloud Debugger

1. Téléchargez et installez [Adobe Experience Cloud Debugger](/help/implement/validate/debugger.md) dans Chrome Web Store.
1. Lancez le débogueur lors du chargement d’une page.
1. Faites défiler jusqu’à la section Audience Manager et recherchez l’UUID Adobe Audience Manager défini sur la page du navigateur active
(`35721780439475290181087231320657663953` dans l’exemple ci-dessous)

   ![Débogueur](assets/aepdebugger.png)

### Méthode 2 : utiliser Chrome Developer Tools (ou les outils de développement d’un autre navigateur)

1. Lancer Chrome Developer Tools avant le chargement d’une page
1. Chargez la page et cochez Applications > Cookies. L’UUID Adobe Audience Manager doit être défini dans le tiers
Cookie Demdex ([adobe.demdex.net](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/reference/demdex-calls) dans l&#39;exemple ci-dessous). Le champ demdex est l’UUID Adobe Audience Manager défini
dans le navigateur (`35721780439475290181087231320657663953` dans l’exemple ci-dessous).

   ![Chrome Developer Tools](assets/devtools.png)

## Utiliser la [!UICONTROL visionneuse du profil du visiteur] d’Audience Manager

L’UUID Adobe Audience Manager du navigateur est défini par défaut lors du chargement de la [!UICONTROL visionneuse du profil du visiteur]. Si vous vérifiez la réalisation des caractéristiques pour d’autres utilisateurs, saisissez un UUID dans le champ UUID et cliquez sur [!UICONTROL Actualiser]. Consultez [Visionneuse du profil du visiteur](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/features/visitor-profile-viewer) pour plus d’informations.

## Afficher les caractéristiques du segment dans [!DNL Audience Manager]

Dans Adobe Audience Manager, la liste des visiteurs avec des ECID pour un segment donné est évaluée tandis qu’Analytics partage des segments avec Experience Cloud.

1. Dans [!DNL Audience Manager], accédez à **[!UICONTROL Données d’audience]** > **[!UICONTROL Caractéristiques]** > **[!UICONTROL Caractéristiques Analytics]**. Un dossier apparaît pour chaque suite de rapports Analytics mappée à votre organisation Experience Cloud. Ces dossiers (pour Caractéristiques, Segments et Sources de données) sont créés lorsque le service principal Profils et audiences / Personnes est lancé ou mis en service.
1. Sélectionnez le dossier de la suite de rapports dans laquelle vous avez créé le segment que vous souhaitez partager avec [!DNL Audience Manager]. Le segment/l’audience que vous avez créé s’affiche. Lorsque vous partagez un segment, deux choses se produisent dans [!DNL Audience Manager] :
   * Une caractéristique est créée, tout d’abord sans contenir de données. Environ Huit heures après la publication du segment dans [!DNL Analytics], la liste des ECID est intégrée et partagée avec [!DNL Audience Manager] et d’autres solutions Experience Cloud.

     ![Caractéristiques d’Audience Manager](assets/aam-traits.png)

   * Un segment à caractère unique est créé. Il utilise la source de données associée à la suite de rapports dans laquelle vous avez publié le segment.
   * L’expiration des caractéristiques est désormais définie sur 16 jours (au lieu de 2 jours auparavant).

## Afficher le segment dans [!DNL Adobe Target]

L’option **[!UICONTROL Publier ce segment dans Experience Cloud]** permet au segment d’être disponible dans la bibliothèque d’audiences personnalisées d’Adobe Target. Un segment créé dans Analytics ou dans Audience Manager peut être utilisé pour des activités dans Target. Vous pouvez par exemple créer des activités de campagne d’après les mesures de conversion d’Analytics et les segments d’audience créés dans Analytics.

Dans Adobe Target :

1. Sélectionnez **[!UICONTROL Audiences]**.
1. Sur la page **[!UICONTROL Audiences]**, recherchez l’audience provenant d’[!DNL Experience Cloud]. Ces audiences peuvent être utilisées dans des activités [!DNL Target].

   ![Audiences cibles](assets/target-audiences.png)
