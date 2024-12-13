---
title: Mesures de qualité des médias en streaming
description: Mesures disponibles lorsque vous activez [!UICONTROL  Qualité du média ] pour une suite de rapports.
feature: Metrics
exl-id: a64829b5-d45b-44c6-80c3-5acf1a6d9919
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 1%

---

# Mesures de qualité des médias en streaming

*Cette page décrit les mesures disponibles lorsque vous activez [!UICONTROL Qualité du média] pour une suite de rapports. Voir [Dimensions de qualité des médias en flux continu](../dimensions/sm-quality.md) pour connaître les dimensions disponibles.*

Les mesures de qualité des médias en flux continu fournissent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais des bibliothèques de collecte de médias en flux continu. L’utilisation de ces mesures nécessite la **[!UICONTROL collection Streaming Media Adobe]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Qualité du média]** sous [Création de rapports multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les mesures suivantes sont disponibles :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Débit moyen | Moyenne pondérée de toutes les valeurs de débit pour la durée de lecture d’une session de lecture. | Fermeture du média | `a.media.qoe.bitrateAverage` |
| Flux impactés par le changement de débit | Valeur booléenne qui se déclenche si le débit change au moins une fois au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.bitrateChange` |
| Changements de débit | Nombre de fois où le débit a changé. | Fermeture du média | `a.media.qoe.bitrateChangeCount` |
| Flux impactés par la mémoire tampon | Valeur booléenne qui se déclenche si la vidéo passe en état de mémoire tampon au moins une fois. | Fermeture du média | `a.media.qoe.buffer` |
| Événements de mémoire tampon | Nombre de fois que la vidéo a été mise en mémoire tampon au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.bufferCount` |
| Durée totale de la mémoire tampon | Durée (en secondes) passée par une vidéo à mettre en tampon tous les événements de mise en tampon. | Fermeture du média | `a.media.qoe.bufferTime` |
| Pertes avant le démarrage | Valeur booléenne qui se déclenche si un utilisateur quitte l’application avant le début du contenu principal d’une vidéo. | Fermeture du média | `a.media.qoe.dropBeforeStart` |
| Images perdues | Nombre entier représentant le nombre total d’images perdues au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.droppedFrameCount` |
| Flux impactés par l’image perdue | Valeur booléenne qui se déclenche lorsqu’une image est déposée au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.droppedFrames` |
| Flux impactés par l’erreur | Valeur booléenne qui se déclenche lorsqu’une vidéo rencontre une erreur à tout moment au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.error` |
| Événements d’erreur | Nombre entier qui représente le nombre total d’erreurs rencontrées au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.errorCount` |
| Heure de début | Durée nécessaire pour démarrer une vidéo, en millisecondes. Adobe convertit et stocke cette valeur en secondes. | Fermeture du média | `a.media.qoe.timeToStart` |
