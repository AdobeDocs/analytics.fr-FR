---
title: Dimensions de cycle de vie mobile
description: Dimensions basées sur les données collectées à l’aide du SDK Mobile.
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
source-git-commit: d940428e1cbe1be6d8263e986e8b641ec18aace1
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 57%

---

# Dimensions de cycle de vie mobile

*Cette page référence les données suivies couramment par le biais du SDK Adobe Experience Platform Mobile. Pour plus d’informations sur les appareils mobiles à l’aide de l’agent utilisateur, voir [Dimensions de recherche mobile](mobile-dimensions.md). Pour les mesures suivies à l’aide du SDK Mobile, voir [Mesures de cycle de vie mobile](../metrics/lifecycle-metrics.md).*

| Nom de la dimension du cycle de vie | Description | Variable de données contextuelles |
| --- | --- | --- |
| [!UICONTROL Date du premier lancement] | | À confirmer |
| [!UICONTROL Nom de l’appareil (SDK)] | | `a.DeviceName` |
| [!UICONTROL Version du système d’exploitation (SDK)] | | `a.OSVersion` |
| [!UICONTROL Résolution (SDK)] | | `a.Resolution` |
| [!UICONTROL Source de l’acquisition] | | `a.referrer.campaign.source` |
| [!UICONTROL ID application] | | `a.AppID` |
| [!UICONTROL Support d’acquisition] | | `a.referrer.campaign.medium` |
| [!UICONTROL Terme de l’acquisition] | | `a.referrer.campaign.term` |
| [!UICONTROL Contenu de l’acquisition] | | `a.refferer.campaign.content` |
| [!UICONTROL Nom de l’acquisition] | | `a.referrer.campaign.name` |
| [!UICONTROL Lieu (jusqu’à 10 km)] | | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL Lieu (jusqu’à 100 m)] | | `a.loc.lat.b` + `a.loc.lon.b` |
| [!UICONTROL Lieu (jusqu’à 1 m)] | | `a.loc.lat.c` + `a.loc.lon.c` |
| [!UICONTROL Nom du point ciblé] | | `a.loc.poi` |
| [!UICONTROL Distance jusqu’au centre du point ciblé] | | `a.loc.dist` |
| [!UICONTROL Numéro de lancement] | | `a.Launches` |
| [!UICONTROL Jours depuis la première utilisation] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Nom de l’action] | | À confirmer |
| [!UICONTROL Valeur de durée de vie (eVar).] | | `a.ltv.amount` |
| [!UICONTROL Balise majeure] | | À confirmer |
| [!UICONTROL Balise mineure] | | À confirmer |
| [!UICONTROL UUID de la balise] | | À confirmer |
| [!UICONTROL Proximité de la balise] | | À confirmer |
| [!UICONTROL Jours depuis la dernière utilisation] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Heure du jour (SDK)] | | `a.HourOfDay` |
| [!UICONTROL Jour de la semaine (SDK)] | | `a.DayOfWeek` |
| [!UICONTROL Identifiant du point ciblé] | | À confirmer |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
