---
title: Dimensions des métadonnées vidéo des services de streaming multimédia
description: Dimensions disponibles lorsque vous activez [!UICONTROL &#x200B; Métadonnées vidéo &#x200B;] pour une suite de rapports.
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 3%

---

# Dimensions des métadonnées vidéo des services de streaming multimédia

*Cette page décrit les dimensions disponibles lorsque vous activez [!UICONTROL Métadonnées vidéo] pour une suite de rapports. Voir [Mesures de métadonnées vidéo des services de streaming multimédia](../metrics/sm-video-metadata.md) pour connaître les mesures disponibles.*

Les dimensions et services de streaming multimédia fournissent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais des bibliothèques de collecte de services de streaming multimédia. L’utilisation de ces dimensions nécessite le **[!UICONTROL module complémentaire Adobe Analytics for Streaming Media]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Métadonnées vidéo]** sous [Rapports multimédia](/help/admin/tools/manage-rs/edit-settings/media-management.md), les dimensions suivantes sont disponibles :

| Nom de la dimension | Description | Envoyé avec | Variable de données contextuelles | Champ XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Chargements d’annonces]** | Type d’annonce publicitaire chargée. | | `a.media.adLoad` | `xdm.mediaCollection.`<br>`sessionDetails.adLoad` |
| **[!UICONTROL Jour]** | Heure de la journée à laquelle le contenu a été diffusé ou lu. Toute valeur de chaîne est prise en charge. | Début du média, Fermer le média | `a.media.dayPart` | `xdm.mediaCollection.`<br>`sessionDetails.dayPart`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.dayPart` |
| **[!UICONTROL Épisode]** | Numéro de l’épisode. | Début du média, Fermer le média | `a.media.episode` | `xdm.mediaCollection.`<br>`sessionDetails.episode`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.episode` |
| **[!UICONTROL Type de flux multimédia]** | Type de flux. | Début du média, Fermer le média | `a.media.feed` | `xdm.mediaCollection.`<br>`sessionDetails.feed`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.feed` |
| **[!UICONTROL Genre]** | Type ou groupement de contenu, tel que défini par le producteur du contenu. Cette dimension prend en charge plusieurs valeurs, délimitées par des virgules. | Début du média, Fermer le média | `a.media.genre` | `xdm.mediaCollection.`<br>`sessionDetails.genre`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.genreList` |
| **[!UICONTROL MVPD]** | Le MVPD fourni par l’authentification Adobe. | Début du média, Fermer le média | `a.media.pass.mvpd` | `xdm.mediaCollection.`<br>`sessionDetails.mvpd`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.mvpd` |
| **[!UICONTROL Réseau]** | Nom du réseau ou du canal. | Début du média, Fermer le média | `a.media.network` | `xdm.mediaCollection.`<br>`sessionDetails.network`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.network` |
| **[!UICONTROL Saison]** | Numéro de la saison à laquelle appartient l’émission. | Début du média, Fermer le média | `a.media.season` | `xdm.mediaCollection.`<br>`sessionDetails.season`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.season` |
| **[!UICONTROL Afficher]** | Nom du programme ou de la série. | Début du média, Fermer le média | `a.media.show` | `xdm.mediaCollection.`<br>`sessionDetails.show`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.show` |
| **[!UICONTROL Afficher le type]** | Nombre entier qui représente le type de contenu.<br>`0` : Épisode complet <br>`1` : Prévisualisation ou bande-annonce<br>`2` : Clip<br>`3` : Autre | Début du média, Fermer le média | `a.media.type` | `xdm.mediaCollection.`<br>`sessionDetails.showType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.showType` |

