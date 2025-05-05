---
title: Mesures de métadonnées vidéo de streaming multimédia
description: Mesures disponibles lorsque vous activez [!UICONTROL &#x200B; Métadonnées vidéo &#x200B;] pour une suite de rapports.
feature: Metrics
exl-id: b2f60a34-e139-4498-bf71-74d291759ef2
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 5%

---

# Mesures de métadonnées vidéo de streaming multimédia

*Cette page décrit les mesures disponibles lorsque vous activez [!UICONTROL Métadonnées vidéo] pour une suite de rapports. Consultez [Dimensions des métadonnées vidéo de streaming multimédia](../dimensions/sm-video-metadata.md) pour connaître les dimensions disponibles.*

Les mesures de métadonnées vidéo Streaming Media fournissent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais des bibliothèques de collecte de médias en flux continu. L’utilisation de ces mesures nécessite la **[!UICONTROL collection Streaming Media Adobe]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Métadonnées vidéo]** sous [Création de rapports multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), la mesure suivante est disponible :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Autorisé | Valeur booléenne qui se déclenche lorsque l’utilisateur est autorisé via l’authentification d’Adobe. | Début du média, Fermer le média | `a.media.pass.auth` |

{style="table-layout:auto"}
