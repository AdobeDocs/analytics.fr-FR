---
title: Dimensions et services de streaming multimédia
description: Dimensions disponibles lorsque vous activez [!UICONTROL Publicités multimédia] pour une suite de rapports.
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 4%

---

# Dimensions et services de streaming multimédia

*Cette page décrit les dimensions disponibles lorsque vous activez [!UICONTROL Publicités multimédia] pour une suite de rapports. Voir [Mesures publicitaires des médias en flux continu](../metrics/sm-ads.md) pour connaître les mesures disponibles.*

Les dimensions et services Streaming Media fournissent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais des bibliothèques Streaming Media Services. L’utilisation de ces dimensions nécessite le **[!UICONTROL module complémentaire Adobe Analytics for Streaming Media]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Publicités multimédia]** sous [Rapports multimédia](/help/admin/tools/manage-rs/edit-settings/media-management.md), les dimensions suivantes sont disponibles :

| Nom de la dimension | Description | Envoyé avec | Variable de données contextuelles | Champ XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Annonce]** | Identifiant unique de la publicité. | Démarrage et fermeture de la publicité | `a.media.ad.`<br>`name` | `xdm.mediaCollection.`<br>`advertisingDetails.name`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.name` |
| **[!UICONTROL Nom de l’annonce (variable)]** | Nom convivial de la publicité. Une dimension de classification nommée « [!UICONTROL Nom de l’annonce] » est également disponible, dans un but similaire. Cette dimension et la classification sont traitées comme deux dimensions distinctes. | Démarrage et fermeture de la publicité | `a.media.ad.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`advertisingDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.friendlyName` |
| **[!UICONTROL Nom du lecteur publicitaire]** | Nom du lecteur qui effectue le rendu de la publicité. | Démarrage et fermeture de la publicité | `a.media.ad.`<br>`playerName` | `xdm.mediaCollection.`<br>`advertisingDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.playerName` |
| **[!UICONTROL Longueur de l’annonce (variable)]** | Durée de la publicité vidéo, en secondes. | Démarrage et fermeture de la publicité | `a.media.ad.`<br>`length` | `xdm.mediaCollection.`<br>`advertisingDetails.length`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.length` |
| **[!UICONTROL capsule publicitaire]** | Identifiant unique de la capsule publicitaire. | Démarrage et fermeture de la publicité | `a.media.ad.`<br>`pod` | |
| **[!UICONTROL Annonce publicitaire dans la capsule]** | Position d’index de l’annonce publicitaire dans la coupure publicitaire parente (indexée sur 0). | Démarrage et fermeture de la publicité | `a.media.ad.`<br>`podPosition` | `xdm.mediaCollection.`<br>`advertisingDetails.podPosition`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.podPosition` |
| **[!UICONTROL Publicitaire]** | Société ou marque présentée dans la publicité. | Démarrage et fermeture de la publicité | `a.media.ad.`<br>`advertiser` | `xdm.mediaCollection.`<br>`advertisingDetails.advertiser`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.advertiser` |
| **[!UICONTROL ID de campagne]** | ID de la campagne publicitaire | Démarrage et fermeture de la publicité | `a.media.ad.`<br>`campaign` | `xdm.mediaCollection.`<br>`advertisingDetails.campaignID`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.campaignID` |

En plus des dimensions ci-dessus, Adobe crée automatiquement les dimensions de classification suivantes. Vous devez charger des données de classification pour afficher les rapports qui utilisent ces dimensions.

| Nom de la classification | Dimension parente | Description |
| --- | --- | --- |
| **[!UICONTROL ID de ressource]** | [[!UICONTROL Contenu]](sm-core.md) | Identifiant unique du contenu de la ressource multimédia. Par exemple, l’identifiant de l’épisode de la série télévisée, l’identifiant de la ressource vidéo ou l’identifiant de l’événement en direct. Ces identifiants sont généralement dérivés d’autorités de métadonnées telles que EIDR, TMS/Gracenote, Rovi, ou d’autres systèmes propriétaires ou internes. |
| **[!UICONTROL Évaluation du contenu]** | [[!UICONTROL Contenu]](sm-core.md) | Évaluation telle que définie par les directives parentales TV. |
| **[!UICONTROL Date de première diffusion]** | [[!UICONTROL Contenu]](sm-core.md) | Date à laquelle le contenu a été diffusé à la télévision pour la première fois. Comme cette dimension de classification est une chaîne, tout format de date est autorisé. Adobe recommande d’utiliser un format de date cohérent, tel que `YYYY-MM-DD`. |
| **[!UICONTROL Première date numérique]** | [[!UICONTROL Contenu]](sm-core.md) | Date à laquelle le contenu a été diffusé pour la première fois sur un canal ou une plateforme numérique. Comme cette dimension de classification est une chaîne, tout format de date est autorisé. Adobe recommande d’utiliser un format de date cohérent, tel que `YYYY-MM-DD`. |
| **[!UICONTROL Longueur de l’annonce]** | [!UICONTROL Annonce] | Durée de la publicité vidéo, en secondes. |
| **[!UICONTROL Nom de l’annonce]** | [!UICONTROL Annonce] | Nom convivial de la publicité. Il s’agit de l’équivalent de classification de « [!UICONTROL Nom de l’annonce (variable)] ». |
| **[!UICONTROL Creative ID]** | [!UICONTROL Annonce] | Identifiant du contenu publicitaire. |
| **[!UICONTROL Nom de la capsule]** | [!UICONTROL capsule publicitaire] | Nom convivial de la capsule publicitaire. |
| **[!UICONTROL Position de la capsule]** | [!UICONTROL capsule publicitaire] | Décalage de la coupure publicitaire dans le contenu, en secondes. |
