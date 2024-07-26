---
title: Dimensions de qualité des médias en flux continu
description: Dimensions disponibles lorsque vous activez [!UICONTROL Qualité du média] pour une suite de rapports.
feature: Dimensions
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 1%

---

# Dimensions de qualité des médias en flux continu

*Cette page décrit les dimensions disponibles lorsque vous activez la [!UICONTROL qualité du média] pour une suite de rapports. Voir [Mesures de qualité des médias en flux continu](../metrics/sm-quality.md) pour connaître les mesures disponibles.*

Les dimensions de qualité des médias en flux continu fournissent des rapports liés à la qualité du contenu que le visiteur consomme. L’utilisation de ces dimensions nécessite le module complémentaire [!UICONTROL Adobe Streaming Media Collection]. Pour plus d’informations, contactez votre équipe de compte d’Adobe.

Lorsque vous activez **[!UICONTROL Qualité du média]** sous [Rapport multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les dimensions suivantes sont disponibles :

| Nom des Dimensions | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Débit moyen | Le débit moyen, en intervalles de compartiments de 100 Kbit/s. Il correspond à la moyenne pondérée de toutes les valeurs de débit par rapport à la durée de lecture d’une session de lecture donnée. | Fermeture du média | `a.media.qoe.bitrateAverageBucket` |
| Changements de débit | Le nombre de changements de débit qui se sont produits au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.bitrateChangeCount` |
| Événements de mémoire tampon | Nombre de fois où le lecteur multimédia a atteint un état de mémoire tampon au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.bufferCount` |
| Durée totale de la mémoire tampon | Durée totale de la mise en mémoire tampon, en secondes. | Fermeture du média | `a.media.qoe.bufferTime` |
| Perte d’images | Nombre total d’images perdues survenues au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.droppedFrameCount` |
| Erreurs | Nombre total d’erreurs qui se sont produites au cours d’une session de lecture. | Fermeture du média | `a.media.qoe.errorCount` |
| ID d’erreur externes | Tous les identifiants d’erreur uniques provenant d’une source externe, comme les erreurs CDN. Vous devez fournir les codes d’erreur ou les identifiants souhaités. Plusieurs ID d’erreur sont autorisés. | Fermeture du média | `a.media.qoe.externalErrors` |
| ID d’erreur du SDK du lecteur | Tous les identifiants d’erreur uniques générés par le SDK du lecteur de contenu. Vous devez fournir les codes d’erreur ou les identifiants souhaités. Plusieurs ID d’erreur sont autorisés. | Fermeture du média | `a.media.qoe.playerSdkErrors` |
| Temps de démarrage | Cette valeur est définie par défaut sur `0` si elle n’est pas définie via QoSObject. Définissez la valeur en millisecondes. Analysis Workspace indique cette dimension en secondes. | Démarrage du média, Fermeture du média | `a.media.qoe.timeToStart` |

{style="table-layout:auto"}
