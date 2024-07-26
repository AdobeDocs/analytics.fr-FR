---
title: Mesures de qualité des médias en flux continu
description: Mesures disponibles lorsque vous activez [!UICONTROL Qualité multimédia] pour une suite de rapports.
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 1%

---

# Mesures de qualité des médias en flux continu

*Cette page décrit les mesures disponibles lorsque vous activez la [!UICONTROL qualité du média] pour une suite de rapports. Voir [Dimensions de qualité des médias en flux continu](../dimensions/sm-quality.md) pour connaître les dimensions disponibles.*

Les mesures de qualité des médias en flux continu offrent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais de bibliothèques de collecte de médias en flux continu. L’utilisation de ces mesures nécessite le **[!UICONTROL module complémentaire Adobe de collecte de médias en flux continu]**. Pour plus d’informations, contactez votre équipe de compte d’Adobe.

Lorsque vous activez **[!UICONTROL Qualité du média]** sous [Rapport multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les mesures suivantes sont disponibles :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Débit moyen | Moyenne pondérée de toutes les valeurs de débit pour la durée de lecture d’une session de lecture. | Fermeture du média | `a.media.qoe.bitrateAverage` |
| Flux touchés par les changements de débit | Valeur booléenne qui se déclenche si le débit binaire change au moins une fois au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.bitrateChange` |
| Changements de débit | Nombre de fois où le débit binaire a changé. | Fermeture du média | `a.media.qoe.bitrateChangeCount` |
| Flux touchés par la mémoire tampon | Valeur booléenne qui se déclenche si la vidéo entre en état de mémoire tampon au moins une fois. | Fermeture du média | `a.media.qoe.buffer` |
| Événements de mémoire tampon | Nombre de fois où la vidéo a été mise en mémoire tampon au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.bufferCount` |
| Durée totale de la mémoire tampon | Durée pendant laquelle une vidéo a passé la mise en mémoire tampon sur tous les événements de mémoire tampon, en secondes. | Fermeture du média | `a.media.qoe.bufferTime` |
| Pertes avant le début | Valeur booléenne qui se déclenche si un utilisateur quitte le site avant que le contenu principal d’une vidéo ne démarre. | Fermeture du média | `a.media.qoe.dropBeforeStart` |
| Perte d’images | Entier représentant le nombre total d’images perdues au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.droppedFrameCount` |
| Flux touchés par la perte d’images | Valeur booléenne qui se déclenche lorsque des images sont perdues au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.droppedFrames` |
| Flux touchés par les erreurs | Valeur booléenne qui se déclenche lorsqu’une vidéo rencontre une erreur à tout moment au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.error` |
| Événements d’erreur | Entier représentant le nombre total d’erreurs survenues au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.errorCount` |
| Temps de démarrage | Durée du démarrage d’une vidéo, en millisecondes. Adobe convertit et stocke cette valeur en secondes. | Fermeture du média | `a.media.qoe.timeToStart` |
