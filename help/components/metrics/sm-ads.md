---
title: Mesures publicitaires pour Streaming Media
description: Mesures disponibles lorsque vous activez [!UICONTROL Media Ads] pour une suite de rapports.
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 5%

---

# Mesures publicitaires pour Streaming Media

*Cette page décrit les mesures disponibles lorsque vous activez [!UICONTROL Publicités multimédia] pour une suite de rapports. Voir [Dimensions d’annonce publicitaire Streaming Media](../dimensions/sm-ads.md) pour connaître les dimensions disponibles.*

Les mesures et médias en flux continu fournissent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais des bibliothèques de collecte de médias en flux continu. L’utilisation de ces mesures nécessite la **[!UICONTROL collection Streaming Media Adobe]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Publicités multimédia]** sous [Rapports multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les mesures suivantes sont disponibles :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Fin de la publicité | Déclenché à la fin d’une publicité vidéo. | Fermeture de la publicité | `a.media.ad.complete` |
| Annonces démarrées | Déclenché lorsqu’une publicité vidéo démarre. | Démarrage de publicité | `a.media.ad.view` |
| Temps passé sur la publicité | Durée totale passée à regarder la publicité, en secondes. | Fermeture de la publicité | `a.media.ad.timePlayed` |
| Temps passé sur le média | Additionne la durée de l’événement pour tous les événements PLAY (contenu principal et publicitaire), en secondes. | Fermeture du média | `a.media.totalTimePlayed` |

{style="table-layout:auto"}
