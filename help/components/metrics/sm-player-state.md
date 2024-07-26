---
title: Mesures de suivi de l’état du lecteur multimédia en flux continu
description: Mesures disponibles lorsque vous activez le [!UICONTROL suivi de l’état du lecteur] pour une suite de rapports.
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 1%

---

# Mesures de suivi de l’état du lecteur multimédia en flux continu

Les mesures de suivi de l’état du lecteur multimédia en flux continu offrent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais de bibliothèques de collecte de médias en flux continu. L’utilisation de ces mesures nécessite le **[!UICONTROL module complémentaire Adobe de collecte de médias en flux continu]**. Pour plus d’informations, contactez votre équipe de compte d’Adobe.

Lorsque vous activez le **[!UICONTROL suivi de l’état du lecteur]** sous [rapport multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les mesures suivantes sont disponibles :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Diffusions affectées par le sous-titrage | Déclenché si au moins un état de sous-titrage codé s’est produit au cours de la session de lecture. | Fermeture du média | `a.media.states.closedcaptioning.set` |
| Nombre de sous-titres codés | Nombre de passages en état de sous-titrage codé de la vidéo. | Fermeture du média | `a.media.states.closedcaptioning.count` |
| Durée totale du sous-titrage codé | Durée pendant laquelle le sous-titrage codé a été affiché, en secondes. | Fermeture du média | `a.media.states.closedcaptioning.time` |
| Diffusions affectées par le mode plein écran | Déclenché si au moins un état Plein écran s’est produit au cours de la session de lecture. | Fermeture du média | `a.media.states.fullscreen.set` |
| Nombre de plein écrans | Nombre de passages en plein écran de la vidéo. | Fermeture du média | `a.media.states.fullscreen.count` |
| Durée totale du plein écran | Durée pendant laquelle la vidéo était en plein écran, en secondes. | Fermeture du média | `a.media.states.fullscreen.time` |
| Diffusions affectées par le mode actif | Déclenché si au moins un état &quot;En point de mires&quot; s’est produit au cours de la session de lecture. | Fermeture du média | `a.media.states.infocus.set` |
| Nombre de cibles | Nombre de passages en mode En point de mires de la vidéo. | Fermeture du média | `a.media.states.infocus.count` |
| Durée totale du ciblage | Durée pendant laquelle la vidéo a été mise en point, en secondes. | Fermeture du média | `a.media.states.infocus.time` |
| Diffusions affectées par le mode muet | Déclenché si au moins un état muet s’est produit au cours de la session de lecture. | Fermeture du média | `a.media.states.mute.set` |
| Nombre d’instances muettes | Nombre de passages en mode muet de la vidéo. | Fermeture du média | `a.media.states.mute.count` |
| Durée totale du mode muet | Durée pendant laquelle la vidéo était en mode muet, en secondes. | Fermeture du média | `a.media.states.mute.time` |
| Diffusions affectées par l’image dans l’image | Déclenché si au moins un état &quot;Image dans l’Image&quot; s’est produit au cours de la session de lecture. | Fermeture du média | `a.media.states.pictureinpicture.set` |
| Nombre d’images | Nombre de passages en mode &quot;Image dans l’Image&quot; de la vidéo. | Fermeture du média | `a.media.states.pictureinpicture.count` |
| Durée totale de l’image | Durée pendant laquelle la vidéo était à l’état &quot;Image dans l’Image&quot;, en secondes. | Fermeture du média | `a.media.states.pictureinpicture.time` |

{style="table-layout:auto"}
