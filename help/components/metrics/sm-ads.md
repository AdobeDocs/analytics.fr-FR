---
title: Services et mesures de streaming multimédia
description: Mesures disponibles lorsque vous activez [!UICONTROL Media Ads] pour une suite de rapports.
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 6%

---

# Services et mesures de streaming multimédia

*Cette page décrit les mesures disponibles lorsque vous activez [!UICONTROL Publicités multimédia] pour une suite de rapports. Consultez [Dimensions et services de streaming multimédia](../dimensions/sm-ads.md) pour connaître les dimensions disponibles.*

Les services et mesures de streaming multimédia fournissent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais des bibliothèques de services de streaming multimédia. L’utilisation de ces mesures nécessite le **[!UICONTROL module complémentaire Adobe Analytics for Streaming Media]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Publicités multimédia]** sous [Rapports multimédia](/help/admin/tools/manage-rs/edit-settings/media-management.md), les mesures suivantes sont disponibles :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles | Champ XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Fin de la publicité]** | Déclenché à la fin d’une publicité vidéo. | Fermeture de la publicité | `a.media.ad.complete` | `xdm.mediaReporting.`<br>`advertisingDetails.isCompleted` |
| **[!UICONTROL La publicité commence]** | Déclenché lorsqu’une publicité vidéo démarre. | Démarrage de publicité | `a.media.ad.view` | `xdm.mediaReporting.`<br>`advertisingDetails.isStarted` |
| **[!UICONTROL Temps passé sur la publicité]** | Durée totale passée à regarder la publicité, en secondes. | Fermeture de la publicité | `a.media.ad.timePlayed` | `xdm.mediaReporting.`<br>`advertisingDetails.timePlayed` |
| **[!UICONTROL Temps passé sur le média]** | Additionne la durée d&#39;événement pour tous les événements &#39;[!UICONTROL Play]&#39; (contenu principal et publicitaire), en secondes. | Fermeture du média | `a.media.totalTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.totalTimePlayed` |
