---
title: Dimensions des métadonnées audio des services de streaming multimédia
description: Dimensions disponibles lorsque vous activez [!UICONTROL &#x200B; Métadonnées audio &#x200B;] pour une suite de rapports.
feature: Dimensions
exl-id: 2e4dc1e9-267b-47a2-b791-23d1e754a2c1
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 6%

---

# Dimensions des métadonnées audio des services de streaming multimédia

Les dimensions et services Streaming Media fournissent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais des bibliothèques Streaming Media Services. L’utilisation de ces dimensions nécessite le **[!UICONTROL module complémentaire Adobe Analytics for Streaming Media]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Métadonnées audio]** sous [Rapports multimédia](/help/admin/tools/manage-rs/edit-settings/media-management.md), les dimensions suivantes sont disponibles :

| Nom de la dimension | Description | Envoyé avec | Variable de données contextuelles | Champ XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL album]** | Nom de l’album. | Début du média, Fermer le média | `a.media.album` | `xdm.mediaCollection.`<br>`sessionDetails.album`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.album` |
| **[!UICONTROL Artiste]** | Nom de l’artiste. | Début du média, Fermer le média | `a.media.artist` | `xdm.mediaCollection.`<br>`sessionDetails.artist`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.artist` |
| **[!UICONTROL Auteur]** | Nom de l’auteur du livre audio. | Début du média, Fermer le média | `a.media.author` | `xdm.mediaCollection.`<br>`sessionDetails.author`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.author` |
| **[!UICONTROL Libellé]** | Nom de la maison de disques. | Début du média, Fermer le média | `a.media.label` | `xdm.mediaCollection.`<br>`sessionDetails.label`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.label` |
| **[!UICONTROL Éditeur]** | Nom de l’éditeur du contenu audio. | Début du média, Fermer le média | `a.media.publisher` | `xdm.mediaCollection.`<br>`sessionDetails.publisher`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.publisher` |
| **[!UICONTROL Station]** | Nom ou ID de la station radio. | Début du média, Fermer le média | `a.media.station` | `xdm.mediaCollection.`<br>`sessionDetails.station`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.station` |
