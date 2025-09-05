---
title: Services et mesures de streaming multimédia
description: Mesures disponibles lorsque vous activez [!UICONTROL Media Ads] pour une suite de rapports.
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 5%

---

# Services et mesures de streaming multimédia

*Cette page décrit les mesures disponibles lorsque vous activez [!UICONTROL Publicités multimédia] pour une suite de rapports. Consultez [Dimensions et services de streaming multimédia](../dimensions/sm-ads.md) pour connaître les dimensions disponibles.*

Les services et mesures de streaming multimédia fournissent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais des bibliothèques de services de streaming multimédia. L’utilisation de ces mesures nécessite le module complémentaire **[!UICONTROL Adobe Analytics for Streaming Media]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Publicités multimédia]** sous [Rapports multimédia](/help/admin/tools/manage-rs/edit-settings/media-management.md), les mesures suivantes sont disponibles :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Fin de la publicité | Déclenché à la fin d’une publicité vidéo. | Fermeture de la publicité | `a.media.ad.complete` |
| Annonces démarrées | Déclenché lorsqu’une publicité vidéo démarre. | Démarrage de publicité | `a.media.ad.view` |
| Temps passé sur la publicité | Durée totale passée à regarder la publicité, en secondes. | Fermeture de la publicité | `a.media.ad.timePlayed` |
| Temps passé sur le média | Additionne la durée de l’événement pour tous les événements PLAY (contenu principal et publicitaire), en secondes. | Fermeture du média | `a.media.totalTimePlayed` |

{style="table-layout:auto"}
