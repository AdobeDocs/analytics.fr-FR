---
title: Dimensions principales des services de streaming multimédia
description: Dimensions disponibles lorsque vous activez [!UICONTROL  Media Core ] pour une suite de rapports.
feature: Dimensions
exl-id: 1316a646-a31a-49a4-a670-d56d90dd462b
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 7%

---

# Dimensions principales des services de streaming multimédia

*Cette page décrit les dimensions disponibles lorsque vous activez [!UICONTROL  Media Core] pour une suite de rapports. Voir [Mesures principales des services de streaming multimédia](../metrics/sm-core.md) pour connaître les mesures disponibles.*

Les dimensions principales des services de streaming multimédia fournissent une fonctionnalité de création de rapports de base aux données collectées via les bibliothèques de services de streaming multimédia. L’utilisation de ces dimensions nécessite le **[!UICONTROL module complémentaire Adobe Analytics for Streaming Media]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Media Core]** sous [Rapports multimédia](/help/admin/tools/manage-rs/edit-settings/media-management.md), les dimensions suivantes sont disponibles :

| Nom de la dimension | Description | Envoyé avec | Variable de données contextuelles | Champ XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Contenu]** | Identifiant du contenu. | Début du média, Fermer le média | `a.media.`<br>`name` | `xdm.mediaCollection.`<br>`sessionDetails.name`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.name` |
| **[!UICONTROL Canal de contenu]** | Station ou canal de distribution sur lequel le contenu est lu. Toute valeur de chaîne est valide. | Début du média, Fermer le média | `a.media.`<br>`channel` | `xdm.mediaCollection.`<br>`sessionDetails.channel`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.channel` |
| **[!UICONTROL Longueur du contenu (variable)]** | Longueur maximale (ou durée) du contenu consommé, en secondes. Cette dimension est requise pour plusieurs mesures, y compris « [!UICONTROL Audience moyenne par minute] ». Si cette dimension n’est pas définie, les mesures dépendantes ne sont pas disponibles.<br><br>Une dimension de classification nommée « [!UICONTROL Longueur de la vidéo] » est également disponible, dans un but similaire. Cette dimension et la classification sont traitées comme deux dimensions distinctes. | Début du média, Fermer le média | `a.media.`<br>`length` | `xdm.mediaCollection.`<br>`sessionDetails.length`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.length` |
| **[!UICONTROL Nom du contenu (variable)]** | Nom convivial du contenu. Une classification nommée « [!UICONTROL Nom de la vidéo] » est également disponible, dans un but similaire. Cette dimension et la classification sont traitées comme deux dimensions distinctes. | Début du média, Fermer le média | `a.media.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`sessionDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.friendlyName` |
| **[!UICONTROL Nom du lecteur de contenu]** | Nom du lecteur de contenu. | Début du média, Fermer le média | `a.media.`<br>`playerName` | `xdm.mediaCollection.`<br>`sessionDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.playerName` |
| **[!UICONTROL Segment de contenu]** | Intervalle qui décrit la partie du contenu qui a été visionnée, en minutes. Le segment correspond aux valeurs min. et max. du curseur de lecture au cours d’une session de lecture. | Fermeture du média | `a.media.`<br>`segment` | `xdm.mediaReporting.`<br>`sessionDetails.segment` |
| **[!UICONTROL Type de contenu]** | Type de contenu. Les valeurs valides sont les suivantes : `song`, `podcast`, `audiobook`, `radio`, `VoD`, `Live`, `Linear`, `UGC`, `DVoD` ou une valeur personnalisée. | Début du média, Fermer le média | `a.contentType` | `xdm.mediaCollection.`<br>`sessionDetails.contentType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.contentType` |
| **[!UICONTROL Chemin du média]** | Chemin d’accès emprunté par le visiteur pour accéder au contenu. | Media Start | `a.media.path` | |
| **[!UICONTROL Type de flux]** | Type de flux. Les valeurs valides comprennent `audio` et `video`. | Début du média, Fermer le média | `a.media.`<br>`streamType` | `xdm.mediaCollection.`<br>`sessionDetails.streamType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.streamType` |

En plus des dimensions ci-dessus, Adobe crée automatiquement les dimensions de classification suivantes. Vous devez charger des données de classification pour afficher les rapports qui utilisent ces dimensions.

| Nom de la classification | Dimension parente | Description |
| --- | --- | --- |
| **[!UICONTROL Longueur de la vidéo]** | [!UICONTROL Contenu] | Longueur maximale (ou durée) du contenu consommé, en secondes. Les mesures qui dépendent de la longueur du contenu ne peuvent pas utiliser cette classification. Vous devez créer une mesure calculée pour obtenir des mesures telles que « [!UICONTROL Audience moyenne par minute] » à l’aide de cette classification. |
| **[!UICONTROL Nom de la vidéo]** | [!UICONTROL Contenu] | Nom convivial du contenu. Il s’agit de l’équivalent de classification de « [!UICONTROL Nom du contenu (variable)] ». |
