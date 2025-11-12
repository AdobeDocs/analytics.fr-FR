---
title: Mesures de métadonnées vidéo des services de streaming multimédia
description: Mesures disponibles lorsque vous activez [!UICONTROL &#x200B; Métadonnées vidéo &#x200B;] pour une suite de rapports.
feature: Metrics
exl-id: b2f60a34-e139-4498-bf71-74d291759ef2
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 7%

---

# Mesures de métadonnées vidéo des services de streaming multimédia

*Cette page décrit les mesures disponibles lorsque vous activez [!UICONTROL Métadonnées vidéo] pour une suite de rapports. Consultez [Dimensions des métadonnées vidéo des services de streaming multimédia](../dimensions/sm-video-metadata.md) pour connaître les dimensions disponibles.*

Les mesures de métadonnées vidéo des services de streaming multimédia fournissent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais des bibliothèques de services de streaming multimédia. L’utilisation de ces mesures nécessite le **[!UICONTROL module complémentaire Adobe Analytics for Streaming Media]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Métadonnées vidéo]** sous [Création de rapports multimédia](/help/admin/tools/manage-rs/edit-settings/media-management.md), la mesure suivante est disponible :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles | Champ XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Autorisé]** | Valeur booléenne qui se déclenche lorsque l’utilisateur est autorisé via l’authentification Adobe. | Début du média, Fermer le média | `a.media.pass.auth` | `xdm.mediaCollection.`<br>`sessionDetails.authorized`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.authorized` |
