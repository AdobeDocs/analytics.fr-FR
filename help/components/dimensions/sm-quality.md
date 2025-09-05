---
title: Dimensions de qualité des services de streaming multimédia
description: Dimensions disponibles lorsque vous activez [!UICONTROL  Qualité du média ] pour une suite de rapports.
feature: Dimensions
exl-id: e3794d8c-3c03-425d-850c-a735b579324b
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# Dimensions de qualité des services de streaming multimédia

*Cette page décrit les dimensions disponibles lorsque vous activez [!UICONTROL Qualité du média] pour une suite de rapports. Voir [Mesures de qualité des services de streaming multimédia](../metrics/sm-quality.md) pour les mesures disponibles.*

Les dimensions de qualité des services de streaming multimédia fournissent des rapports liés à la qualité du contenu utilisé par le visiteur. L’utilisation de ces dimensions nécessite le module complémentaire [!UICONTROL Adobe Analytics for Streaming Media]. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Qualité du média]** sous [Création de rapports multimédia](/help/admin/tools/manage-rs/edit-settings/media-management.md), les dimensions suivantes sont disponibles :

| Nom des dimensions | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Débit moyen | Débit moyen, dans des intervalles de compartiment de 100 KBPS. Il est calculé comme la moyenne pondérée de toutes les valeurs de débit par rapport à la durée de lecture pour une session de lecture donnée. | Fermeture du média | `a.media.qoe.bitrateAverageBucket` |
| Changements de débit | Nombre de changements de débit qui se sont produits au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.bitrateChangeCount` |
| Événements de mémoire tampon | Nombre de fois où le lecteur multimédia est entré en état de mémoire tampon au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.bufferCount` |
| Durée totale de la mémoire tampon | Durée totale de la mise en mémoire tampon, en secondes. | Fermeture du média | `a.media.qoe.bufferTime` |
| Images perdues | Nombre total d’images perdues au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.droppedFrameCount` |
| Erreurs | Nombre total d’erreurs qui se sont produites au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.errorCount` |
| ID d&#39;erreurs externes | Tous les identifiants d’erreur uniques provenant de toute source externe, tels que les erreurs CDN. Vous devez fournir les codes d’erreur ou les identifiants souhaités. Plusieurs identifiants d’erreur sont autorisés. | Fermeture du média | `a.media.qoe.externalErrors` |
| ID d’erreur du SDK du lecteur | Tous les identifiants d’erreur uniques générés par le lecteur de contenu SDK. Vous devez fournir les codes d’erreur ou les identifiants souhaités. Plusieurs identifiants d’erreur sont autorisés. | Fermeture du média | `a.media.qoe.playerSdkErrors` |
| Heure de début | Cette valeur est définie par défaut sur `0` si elle n’est pas définie via QoSObject. Définissez la valeur en millisecondes. Analysis Workspace signale cette dimension en secondes. | Début du média, Fermer le média | `a.media.qoe.timeToStart` |

{style="table-layout:auto"}
