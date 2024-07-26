---
title: Mesures de métadonnées vidéo des médias en flux continu
description: Mesures disponibles lorsque vous activez les [!UICONTROL métadonnées vidéo] pour une suite de rapports.
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 5%

---

# Mesures de métadonnées vidéo des médias en flux continu

*Cette page décrit les mesures disponibles lorsque vous activez les [!UICONTROL métadonnées vidéo] pour une suite de rapports. Voir [Dimensions des métadonnées vidéo de médias en flux continu](../dimensions/sm-video-metadata.md) pour connaître les dimensions disponibles.*

Les mesures de métadonnées vidéo de médias en flux continu offrent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais de bibliothèques de collecte de médias en flux continu. L’utilisation de ces mesures nécessite le **[!UICONTROL module complémentaire Adobe de collecte de médias en flux continu]**. Pour plus d’informations, contactez votre équipe de compte d’Adobe.

Lorsque vous activez les **[!UICONTROL métadonnées vidéo]** sous [Rapports multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), la mesure suivante est disponible :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Autorisé | Valeur booléenne qui se déclenche lorsque l’utilisateur est autorisé via l’authentification d’Adobe. | Démarrage du média, Fermeture du média | `a.media.pass.auth` |

{style="table-layout:auto"}
