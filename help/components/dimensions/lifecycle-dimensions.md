---
title: Dimensions du cycle de vie mobile
description: Dimensions basées sur les données collectées à l’aide de Mobile SDK.
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
TQID: 'https://experienceleague.adobe.com/VUN8x5eMzIfJ9VGw76v2pWfKWU7b-ct-kI6liwWTObw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 6fd4400b33fcfc8bc3cd3ffc54fa738fef3441ef
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 8%
---
# Dimensions du cycle de vie mobile

>[!BEGINSHADEBOX]

*Cette page fait référence aux données suivies couramment via Adobe Experience Platform Mobile SDK. Pour plus d’informations sur les appareils mobiles à l’aide de l’agent utilisateur, voir [Dimensions de recherche mobile](mobile-dimensions.md). Pour les mesures suivies à l’aide de Mobile SDK, voir [Mesures de cycle de vie mobile](../metrics/lifecycle-metrics.md).*

>[!ENDSHADEBOX]

| Nom de la dimension du cycle de vie | Description | Variable de données contextuelles |
| --- | --- | --- |
| **[!UICONTROL Première date de lancement]** | Date à laquelle l’application a été exécutée pour la première fois après avoir été installée ou réinstallée, au format `M/d/yyyy`. | `a.InstallDate` |
| **[!UICONTROL Nom de l’appareil (SDK)]** | Nom de l’appareil collecté par SDK. | `a.DeviceName` |
| **[!UICONTROL Version du système d’exploitation (SDK)]** | Nom et version du système d’exploitation collectés par SDK. | `a.OSVersion` |
| **[!UICONTROL Résolution (SDK)]** | Résolution de l’écran de l’appareil en pixels, exprimée en largeur x hauteur. | `a.Resolution` |
| Source d’acquisition ]****[!UICONTROL  | Référent d’origine pour une campagne d’acquisition d’application, telle qu’une newsletter ou un réseau de médias sociaux. | `a.referrer.campaign.source` |
| **[!UICONTROL ID de l’application]** | Nom et version de l’application, au format `AppName BundleVersion (app version code)`. Par exemple : `MyAppName 1.1(1)`. | `a.AppID` |
| Medium d’acquisition ]****[!UICONTROL  | Support marketing pour une campagne d’acquisition d’application, telle qu’une bannière ou un e-mail. | `a.referrer.campaign.medium` |
| **[!UICONTROL Terme d’acquisition]** | Mots-clés payants ou autres termes associés à une campagne d’acquisition d’application. | `a.referrer.campaign.term` |
| **[!UICONTROL Contenu d’acquisition]** | Nom ou ID du contenu qui affichait le lien d’acquisition de l’application. | `a.referrer.campaign.content` |
| **[!UICONTROL Nom de l’acquisition]** | Nom de la campagne d’acquisition de l’application. | `a.referrer.campaign.name` |
| **[!UICONTROL Lieu (jusqu’à 10 km)]** | Latitude et longitude du visiteur, exactes à la première décimale. Par exemple, `040.9` `-111.9`. | `a.loc.lat.a` + `a.loc.lon.a` |
| **[!UICONTROL Lieu (jusqu’à 100 m)]** | Latitude et longitude du visiteur, exactes à la troisième décimale. Par exemple, `040.932` `-111.931`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| **[!UICONTROL Lieu (jusqu’à 1 m)]** | Latitude et longitude du visiteur, exactes à la cinquième décimale. Par exemple, `040.93231` `-111.93152`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| **[!UICONTROL Nom du point ciblé]** | Nom du point d’intérêt dans lequel se trouve l’appareil. Lorsque vous utilisez l’extension [Places](https://developer.adobe.com/client-sdks/solution/places/), cette valeur correspond au nom de la région Places. | `a.loc.poi` |
| **[!UICONTROL Distance jusqu’au centre du point ciblé]** | Distance entre l’appareil et le centre du point d’intérêt dans lequel se trouve l’appareil. | `a.loc.dist` |
| **[!UICONTROL Numéro de lancement]** | Nombre de fois où l’application a été lancée ou retirée de l’arrière-plan. | `a.Launches` |
| **[!UICONTROL Jours depuis la première utilisation]** | Nombre de jours écoulés depuis la première exécution de l’application. | `a.DaysSinceFirstUse` |
| **[!UICONTROL Nom de l’action]** | Nom de l’action envoyée dans un appel `trackAction`. | `a.action` |
| **[!UICONTROL Valeur de durée de vie (evar)]** | Valeur de durée de vie d’un utilisateur, telle que les achats de durée de vie, les vues de publicités, les vidéos terminées ou les partages sur les réseaux sociaux. | `a.ltv.amount` |
| **[!UICONTROL Balise principale]** | Identifiant principal de la balise dont se trouve à proximité l’appareil. | `a.beacon.major` |
| **[!UICONTROL Balise mineure]** | ID mineur de la balise à proximité de l’appareil. | `a.beacon.minor` |
| **[!UICONTROL UUID de balise]** | UUID de la balise à proximité de l’appareil. | `a.beacon.uuid` |
| **[!UICONTROL Proximité de la balise]** | Proximité de l’appareil par rapport à la balise : `0` (inconnu), `1` (immédiat), `2` (proche) ou `3` (éloigné). | `a.beacon.prox` |
| **[!UICONTROL Jours depuis la dernière utilisation]** | Nombre de jours écoulés depuis la dernière utilisation de l’application. | `a.DaysSinceLastUse` |
| **[!UICONTROL Heure de la journée (SDK)]** | Heure de lancement de l’application, au format 24 heures. Utile pour la répartition du temps afin de déterminer les heures d’utilisation de pointe. | `a.HourOfDay` |
| **[!UICONTROL Jour de la semaine (SDK)]** | Jour de la semaine où l’application a été lancée. | `a.DayOfWeek` |
| **[!UICONTROL ID du point ciblé]** | L’identifiant du point ciblé sur lequel se trouve l’appareil. Lorsque vous utilisez l’extension [Places](https://developer.adobe.com/client-sdks/solution/places/), cette valeur correspond à l’identifiant de la région Places. | `a.loc.poi.id` |

>[!NOTE]
>
>Certaines de ces dimensions sont renseignées par des méthodes dans l’ancien Mobile Services SDK (4.x), qui n’est plus pris en charge. Adobe Experience Platform Mobile SDK ne les renseigne pas automatiquement :
>
>* **Dimensions d’acquisition** ([!UICONTROL Acquisition Source], [!UICONTROL Medium], [!UICONTROL Term], [!UICONTROL Content] et [!UICONTROL Name]) : renseigné par Acquisition d’application mobile, que le [ ](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/comparison/) de SDK mobile ne prend pas en charge.
>* **[!UICONTROL Emplacement] dimensions et [!UICONTROL Distance par rapport au centre du point ciblé]** : renseigné par la méthode de `trackLocation` 4.x. Le SDK mobile remplace cette méthode par l’extension [Places](https://developer.adobe.com/client-sdks/solution/places/), qui renseigne [!UICONTROL Nom du point ciblé] et [!UICONTROL ID du point ciblé].
>* **[!UICONTROL Valeur de durée de vie (evar)]** : renseignée par la méthode `trackLifetimeValueIncrease` 4.x.
>* **Dimensions de balise** ([!UICONTROL Balise majeure], [!UICONTROL Mineure], [!UICONTROL UUID] et [!UICONTROL Proximité]) : renseignée par la méthode 4.x `trackBeacon`. Pour envoyer des données de balise avec Mobile SDK, voir [Balises de tracking](https://developer.adobe.com/client-sdks/solution/adobe-analytics/track-beacon/).
>
>Voir [Migration de la bibliothèque mobile Adobe (v4) vers Experience Platform Analytics](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/analytics/) pour plus d’informations.
