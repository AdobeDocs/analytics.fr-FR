---
title: Dimensions du cycle de vie mobile
description: Dimensions basées sur les données collectées à l’aide de Mobile SDK.
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 23%

---

# Dimensions du cycle de vie mobile

*Ces données de référence de page sont généralement suivies via Adobe Experience Platform Mobile SDK. Pour plus d’informations sur les appareils mobiles à l’aide de l’agent utilisateur, voir [Dimensions de recherche mobile](mobile-dimensions.md). Pour les mesures suivies à l’aide de Mobile SDK, voir [Mesures de cycle de vie mobile](../metrics/lifecycle-metrics.md).*

| Nom de la dimension du cycle de vie | Description | Variable de données contextuelles |
| --- | --- | --- |
| [!UICONTROL Première date de lancement] | | |
| [!UICONTROL Nom de l’appareil (SDK)] | | `a.DeviceName` |
| [!UICONTROL Version du système d’exploitation (SDK)] | | `a.OSVersion` |
| [!UICONTROL Résolution (SDK)] | | `a.Resolution` |
| [!UICONTROL Source d’acquisition] | | `a.referrer.campaign.source` |
| [!UICONTROL ID de l’application] | | `a.AppID` |
| [!UICONTROL Medium d’acquisition] | | `a.referrer.campaign.medium` |
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
