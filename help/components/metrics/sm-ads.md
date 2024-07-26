---
title: Mesures publicitaires des médias en flux continu
description: Mesures disponibles lorsque vous activez [!UICONTROL Media Ads] pour une suite de rapports.
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 5%

---

# Mesures publicitaires des médias en flux continu

*Cette page décrit les mesures disponibles lorsque vous activez [!UICONTROL Media Ads] pour une suite de rapports. Voir [Dimensions de publicité du média en flux continu](../dimensions/sm-ads.md) pour connaître les dimensions disponibles.*

Les mesures publicitaires de médias en flux continu offrent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais de bibliothèques de collecte de médias en flux continu. L’utilisation de ces mesures nécessite le **[!UICONTROL module complémentaire Adobe de collecte de médias en flux continu]**. Pour plus d’informations, contactez votre équipe de compte d’Adobe.

Lorsque vous activez **[!UICONTROL Media Ads]** sous [Media reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les mesures suivantes sont disponibles :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Fin de la publicité | Déclenché à la fin d’une publicité vidéo. | Fermer la publicité | `a.media.ad.complete` |
| Démarrages de publicité | Déclenché au démarrage d’une publicité vidéo. | Démarrage de publicité | `a.media.ad.view` |
| Temps passé sur la publicité | Durée totale passée à regarder la publicité, en secondes. | Fermer la publicité | `a.media.ad.timePlayed` |
| Temps passé sur le média | Totalise la durée de l’événement pour tous les événements PLAY (contenu principal et publicitaire), en secondes. | Fermeture du média | `a.media.totalTimePlayed` |

{style="table-layout:auto"}
