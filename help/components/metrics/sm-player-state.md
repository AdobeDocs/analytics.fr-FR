---
title: Mesures de suivi de l’état du lecteur Streaming Media
description: Mesures disponibles lorsque vous activez le [!UICONTROL suivi de l’état du lecteur] pour une suite de rapports.
feature: Metrics
exl-id: 324936cc-0c7a-4710-a618-b24cc6a2c2cf
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---

# Mesures de suivi de l’état du lecteur Streaming Media

Les mesures de suivi de l’état du lecteur Streaming Media fournissent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais des bibliothèques de collecte de médias en flux continu. L’utilisation de ces mesures nécessite la **[!UICONTROL collection Streaming Media Adobe]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez le **[!UICONTROL suivi de l’état du lecteur]** sous [rapports multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les mesures suivantes sont disponibles :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Flux affectés par le sous-titrage | Déclenché si au moins un état de sous-titrage codé s’est produit pendant une session de lecture. | Fermeture du média | `a.media.states.closedcaptioning.set` |
| Nombre de sous-titres | Nombre de fois où la vidéo est entrée en statut Sous-titrage. | Fermeture du média | `a.media.states.closedcaptioning.count` |
| Durée totale du sous-titrage | Durée pendant laquelle la vidéo a été dans un état de sous-titrage codé, en secondes. | Fermeture du média | `a.media.states.closedcaptioning.time` |
| Flux impactés par le plein écran | Déclenché si au moins un état Plein écran s’est produit au cours d’une session de lecture. | Fermeture du média | `a.media.states.fullscreen.set` |
| Nombre de pages plein écran | Nombre de fois où la vidéo est entrée en mode Plein écran. | Fermeture du média | `a.media.states.fullscreen.count` |
| Durée totale en plein écran | Durée pendant laquelle la vidéo a été en mode Plein écran, en secondes. | Fermeture du média | `a.media.states.fullscreen.time` |
| Flux impactés par dans le focus | Déclenché si au moins un état Activé s’est produit au cours d’une session de lecture. | Fermeture du média | `a.media.states.infocus.set` |
| Nombre d’éléments ciblés | Nombre de fois où la vidéo est entrée en mode Mise au point. | Fermeture du média | `a.media.states.infocus.count` |
| Durée totale du focus | Durée pendant laquelle la vidéo a été mise au point, en secondes. | Fermeture du média | `a.media.states.infocus.time` |
| Flux impactés par le mode silencieux | Déclenché si au moins un état Silence s’est produit au cours d’une session de lecture. | Fermeture du média | `a.media.states.mute.set` |
| Nombre de mises en sourdine | Nombre de fois où la vidéo est entrée en mode Silence. | Fermeture du média | `a.media.states.mute.count` |
| Durée totale du son muet | Durée pendant laquelle la vidéo a été mise en sourdine, en secondes. | Fermeture du média | `a.media.states.mute.time` |
| Flux impactés par l’image dans l’image | Déclenché si au moins une image dans l’état Image s’est produite au cours d’une session de lecture. | Fermeture du média | `a.media.states.pictureinpicture.set` |
| Image dans le nombre d’images | Nombre de fois où la vidéo est entrée dans un état Image dans l’image. | Fermeture du média | `a.media.states.pictureinpicture.count` |
| Durée totale de l&#39;image dans l&#39;image | Durée pendant laquelle la vidéo a été à l’état Image dans l’image, en secondes. | Fermeture du média | `a.media.states.pictureinpicture.time` |

{style="table-layout:auto"}
