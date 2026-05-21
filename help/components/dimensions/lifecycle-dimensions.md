---
title: Dimensions du cycle de vie mobile
description: Dimensions basées sur les données collectées à l’aide de Mobile SDK.
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
TQID: https://experienceleague.adobe.com/VUN8x5eMzIfJ9VGw76v2pWfKWU7b-ct-kI6liwWTObw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 180
ht-degree: 25%

---

# Dimensions du cycle de vie mobile

*Ces données de référence de page sont généralement suivies via Adobe Experience Platform Mobile SDK. Pour plus d’informations sur les appareils mobiles à l’aide de l’agent utilisateur, voir [Dimensions de recherche mobile](mobile-dimensions.md). Pour les mesures suivies à l’aide de Mobile SDK, voir [Mesures de cycle de vie mobile](../metrics/lifecycle-metrics.md).*

| Nom de la dimension du cycle de vie | Description | Variable de données contextuelles |
| --- | --- | --- |
| [!UICONTROL Première date de lancement] | | |
| [!UICONTROL Nom de l’appareil (SDK)] | | `a.DeviceName` |
| [!UICONTROL Version du système d’exploitation (SDK)] | | `a.OSVersion` |
| [!UICONTROL Résolution (SDK)] | | `a.Resolution` |
| Source d’acquisition | | `a.referrer.campaign.source` |
| [!UICONTROL ID de l’application] | | `a.AppID` |
| Medium d’acquisition | | `a.referrer.campaign.medium` |
| [!UICONTROL Terme d’acquisition] | | `a.referrer.campaign.term` |
| [!UICONTROL Contenu d’acquisition] | | `a.refferer.campaign.content` |
| [!UICONTROL Nom de l’acquisition] | | `a.referrer.campaign.name` |
| [!UICONTROL Lieu (jusqu’à 10 km)] | Latitude et longitude du visiteur, exactes à la première décimale. Par exemple, `040.9` `-111.9`. | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL Lieu (jusqu’à 100 m)] | Latitude et longitude du visiteur, exactes à la troisième décimale. Par exemple, `040.932` `-111.931`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| [!UICONTROL Lieu (jusqu’à 1 m)] | Latitude et longitude du visiteur, exactes à la cinquième décimale. Par exemple, `040.93231` `-111.93152`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| [!UICONTROL Nom du point ciblé] | | `a.loc.poi` |
| [!UICONTROL Distance jusqu’au centre du point ciblé] | | `a.loc.dist` |
| [!UICONTROL Numéro de lancement] | | `a.Launches` |
| [!UICONTROL Jours depuis la première utilisation] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Nom de l’action] | | |
| [!UICONTROL Valeur de durée de vie (evar)] | | `a.ltv.amount` |
| [!UICONTROL Balise principale] | | |
| [!UICONTROL Balise mineure] | | |
| [!UICONTROL UUID de balise] | | |
| [!UICONTROL Proximité de la balise] | | |
| [!UICONTROL Jours depuis la dernière utilisation] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Heure de la journée (SDK)] | | `a.HourOfDay` |
| [!UICONTROL Jour de la semaine (SDK)] | | `a.DayOfWeek` |
| [!UICONTROL ID du point ciblé] | | |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
