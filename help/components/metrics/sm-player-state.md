---
title: Mesures de suivi de l’état du lecteur des services de streaming multimédia
description: Mesures disponibles lorsque vous activez le [!UICONTROL suivi de l’état du lecteur] pour une suite de rapports.
feature: Metrics
exl-id: 324936cc-0c7a-4710-a618-b24cc6a2c2cf
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 2%

---

# Mesures de suivi de l’état du lecteur des services de streaming multimédia

Les mesures de suivi de l’état du lecteur des services de streaming multimédia fournissent une fonctionnalité de création de rapports supplémentaire à la collecte de données par le biais des bibliothèques de services de streaming multimédia. L’utilisation de ces mesures nécessite le **[!UICONTROL module complémentaire Adobe Analytics for Streaming Media]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez le **[!UICONTROL suivi de l’état du lecteur]** sous [rapports multimédia](/help/admin/tools/manage-rs/edit-settings/media-management.md), les mesures suivantes sont disponibles :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles | Champ XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Flux affectés par le sous-titrage]** | Déclenché si au moins un état de sous-titrage codé s’est produit pendant une session de lecture. | Fermeture du média | `a.media.states.`<br>`closedcaptioning.set` | `mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Nombre de légendes]** | Nombre de fois où la vidéo est entrée en statut Sous-titrage. | Fermeture du média | `a.media.states.`<br>`closedcaptioning.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Durée totale du sous-titrage]** | Durée pendant laquelle la vidéo a été dans un état de sous-titrage codé, en secondes. | Fermeture du média | `a.media.states.`<br>`closedcaptioning.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Flux affectés par le plein écran]** | Déclenché si au moins un état Plein écran s’est produit au cours d’une session de lecture. | Fermeture du média | `a.media.states.`<br>`fullscreen.set` | `xdm.mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Nombre de pages plein écran]** | Nombre de fois où la vidéo est entrée en mode Plein écran. | Fermeture du média | `a.media.states.`<br>`fullscreen.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Durée totale en plein écran]** | Durée pendant laquelle la vidéo a été en mode Plein écran, en secondes. | Fermeture du média | `a.media.states.`<br>`fullscreen.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Flux affectés par dans le focus]** | Déclenché si au moins un état Activé s’est produit au cours d’une session de lecture. | Fermeture du média | `a.media.states.`<br>`infocus.set` | `mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Nombre de focus]** | Nombre de fois où la vidéo est entrée en mode Mise au point. | Fermeture du média | `a.media.states.`<br>`infocus.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Durée totale du focus]** | Durée pendant laquelle la vidéo a été mise au point, en secondes. | Fermeture du média | `a.media.states.`<br>`infocus.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Flux affectés par le mode muet]** | Déclenché si au moins un état Silence s’est produit au cours d’une session de lecture. | Fermeture du média | `a.media.states.`<br>`mute.set` | `xdm.mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Nombre de mises en sourdine]** | Nombre de fois où la vidéo est entrée en mode Silence. | Fermeture du média | `a.media.states.`<br>`mute.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Durée totale du son muet]** | Durée pendant laquelle la vidéo a été mise en sourdine, en secondes. | Fermeture du média | `a.media.states.`<br>`mute.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Flux affectés par l’image dans l’image]** | Déclenché si au moins une image dans l’état Image s’est produite au cours d’une session de lecture. | Fermeture du média | `a.media.states.`<br>`pictureinpicture.set` | `mediaReporting.states.`<br>`[*].isSet` |
| **[!UICONTROL Image dans le nombre d’images]** | Nombre de fois où la vidéo est entrée dans un état Image dans l’image. | Fermeture du média | `a.media.states.`<br>`pictureinpicture.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Durée totale de l&#39;image dans l&#39;image]** | Durée pendant laquelle la vidéo a été à l’état Image dans l’image, en secondes. | Fermeture du média | `a.media.states.`<br>`pictureinpicture.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
