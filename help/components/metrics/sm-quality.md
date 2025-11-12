---
title: Mesures de qualité des services de streaming multimédia
description: Mesures disponibles lorsque vous activez [!UICONTROL &#x200B; Qualité du média &#x200B;] pour une suite de rapports.
feature: Metrics
exl-id: a64829b5-d45b-44c6-80c3-5acf1a6d9919
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 2%

---

# Mesures de qualité des services de streaming multimédia

*Cette page décrit les mesures disponibles lorsque vous activez [!UICONTROL Qualité du média] pour une suite de rapports. Consultez [Dimensions de qualité des services de streaming multimédia](../dimensions/sm-quality.md) pour connaître les dimensions disponibles.*

Les mesures de qualité des services de streaming multimédia fournissent des fonctionnalités de reporting supplémentaires à la collecte de données par le biais des bibliothèques de services de streaming multimédia. L’utilisation de ces mesures nécessite le **[!UICONTROL module complémentaire Adobe Analytics for Streaming Media]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Qualité du média]** sous [Création de rapports multimédia](/help/admin/tools/manage-rs/edit-settings/media-management.md), les mesures suivantes sont disponibles :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles | Champ XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Débit moyen]** | Moyenne pondérée de toutes les valeurs de débit pour la durée de lecture d’une session de lecture. | Fermeture du média | `a.media.qoe.`<br>`bitrateAverage` | `xdm.mediaReporting.`<br>`qoeDataDetails.bitrateAverage` |
| **[!UICONTROL Flux affectés par le changement de débit]** | Valeur booléenne qui se déclenche si le débit change au moins une fois au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.`<br>`bitrateChange` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasBitrateChangeImpactedStreams` |
| **[!UICONTROL Modifications de débit]** | Nombre de fois où le débit a changé. | Fermeture du média | `a.media.qoe.`<br>`bitrateChangeCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrateChangeCount`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateChangeCount` |
| **[!UICONTROL Flux impactés par la mise en mémoire tampon]** | Valeur booléenne qui se déclenche si la vidéo passe en état de mémoire tampon au moins une fois. | Fermeture du média | `a.media.qoe.`<br>`buffer` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasBufferImpactedStreams` |
| **[!UICONTROL Événements de mémoire tampon]** | Nombre de fois que la vidéo a été mise en mémoire tampon au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.`<br>`bufferCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.bufferCount` |
| **[!UICONTROL Durée totale du tampon]** | Durée (en secondes) passée par une vidéo à mettre en tampon tous les événements de mise en tampon. | Fermeture du média | `a.media.qoe.`<br>`bufferTime` | `xdm.mediaReporting.`<br>`qoeDataDetails.bufferTime` |
| **[!UICONTROL Pertes avant le démarrage]** | Valeur booléenne qui se déclenche si un utilisateur quitte l’application avant le début du contenu principal d’une vidéo. | Fermeture du média | `a.media.qoe.`<br>`dropBeforeStart` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`isDroppedBeforeStart` |
| **[!UICONTROL Images perdues]** | Nombre entier représentant le nombre total d’images perdues au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.`<br>`droppedFrameCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.droppedFrames`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.droppedFrames` |
| **[!UICONTROL Flux impactés par l’image perdue]** | Valeur booléenne qui se déclenche lorsqu’une image est déposée au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.`<br>`droppedFrames` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasDroppedFrameImpactedStreams` |
| **[!UICONTROL Flux impactés par l’erreur]** | Valeur booléenne qui se déclenche lorsqu’une vidéo rencontre une erreur à tout moment au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.`<br>`error` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasErrorImpactedStreams` |
| **[!UICONTROL Événements d’erreur]** | Nombre entier qui représente le nombre total d’erreurs rencontrées au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.`<br>`errorCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.errorCount` |
| **[!UICONTROL Heure de commencer]** | Durée nécessaire pour démarrer une vidéo, en millisecondes. Adobe convertit et stocke cette valeur en secondes. | Fermeture du média | `a.media.qoe.`<br>`timeToStart` | `xdm.mediaCollection.`<br>`qoeDataDetails.timeToStart`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.timeToStart` |
