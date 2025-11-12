---
title: Mesures principales des services de streaming multimédia
description: Mesures disponibles lorsque vous activez [!UICONTROL  Media Core ] pour une suite de rapports.
feature: Metrics
exl-id: f4ff5f84-18b6-4e67-b808-133faeaf8605
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 2%

---

# Mesures principales des services de streaming multimédia

*Cette page décrit les mesures disponibles lorsque vous activez [!UICONTROL Media Core] pour une suite de rapports. Consultez [Dimensions principales des services de streaming multimédia](../dimensions/sm-core.md) pour connaître les dimensions disponibles.*

Les mesures principales des services de streaming multimédia fournissent une fonctionnalité de création de rapports de base aux données collectées via les bibliothèques de collecte des services de streaming multimédia. L’utilisation de ces mesures nécessite le **[!UICONTROL module complémentaire Adobe Analytics for Streaming Media]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Media Core]** sous [Rapports multimédia](/help/admin/tools/manage-rs/edit-settings/media-management.md), les mesures suivantes sont disponibles :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles | Champ XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Audience moyenne par minute]** | Temps total passé sur un élément de contenu donné, divisé par sa durée pour toutes ses sessions de lecture.<br>`[Time spent] / [Media length]` | Fermeture du média | `a.media.`<br>`averageMinuteAudience` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`averageMinuteAudience` |
| **[!UICONTROL Fin du contenu]** | Se déclenche lorsqu’un élément de contenu se termine. Cette mesure ne signifie pas nécessairement qu’ils ont consulté l’intégralité du contenu ; ils auraient pu l’ignorer. Cela signifie uniquement qu’ils ont atteint la fin du contenu. | | `a.media.complete` | `xdm.mediaReporting.`<br>`sessionDetails.isCompleted` |
| **[!UICONTROL Flux impactés en pause]** | Valeur booléenne qui se déclenche si une ou plusieurs pauses se sont produites pendant la lecture du contenu. | Fermeture du média | `a.media.pause` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasPauseImpactedStreams` |
| **[!UICONTROL Événements Pause]** | Nombre de pauses survenues au cours d’une session de lecture. | Fermeture du média | `a.media.pauseCount` | `xdm.mediaReporting.`<br>`sessionDetails.pauseCount` |
| **[!UICONTROL Durée totale de la pause]** | Durée totale de tous les événements de pause, en secondes. | Fermeture du média | `a.media.pauseTime` | `xdm.mediaReporting.`<br>`sessionDetails.pauseTime` |
| **[!UICONTROL Le contenu démarre]** | La première image du média est consommée. Si un utilisateur ou une utilisatrice tombe pendant une publicité ou pendant la mise en mémoire tampon, cet événement ne se déclenche pas. | Fermeture du média | `a.media.play` | `xdm.mediaReporting.`<br>`sessionDetails.isPlayed` |
| **[!UICONTROL marqueur de progression de 10 %]**<br>**[!UICONTROL marqueur de progression de 25 %]**<br>**[!UICONTROL marqueur de progression de 50 %]**<br>**[!UICONTROL marqueur de progression de 75 %]**<br>**[!UICONTROL marqueur de progression de 95 %]** | Le curseur de lecture transmet le marqueur de contenu indiqué en fonction de la longueur. Chaque marqueur n’est comptabilisé qu’une seule fois, même si la recherche est effectuée à rebours. Si vous effectuez une recherche vers l’avant, les marqueurs ignorés ne sont pas comptabilisés. | Fermeture du média | `a.media.progress10`<br>`a.media.progress25`<br>`a.media.progress50`<br>`a.media.progress75`<br>`a.media.progress95` | `xdm.mediaReporting.`<br>`sessionDetails.hasProgress10`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress25`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress50`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress75`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress95` |
| **[!UICONTROL Reprise du contenu]** | Valeur booléenne qui se déclenche lorsque le contenu est repris après une période de plus de 30 minutes de mise en tampon, de pause ou de blocage. Se déclenche également si le lecteur le définit sur le trackPlay VideoInfo. | Fermeture du média | `a.media.resume` | `xdm.mediaCollection.`<br>`sessionDetails.hasResume`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasResume` |
| **[!UICONTROL Vues de segment de contenu]** | Valeur booléenne qui se déclenche sur la première image du segment affiché. | Fermeture du média | `a.media.segmentView` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasSegmentView` |
| **[!UICONTROL Démarrage des médias]** | Valeur booléenne qui se déclenche lors du chargement initial du média. Cet événement inclut les publicités, la mise en mémoire tampon et les erreurs. | Media Start | `a.media.view` | `xdm.mediaReporting.`<br>`sessionDetails.isViewed` |
| **[!UICONTROL Temps passé sur le contenu]** | Durée totale des événements de type PLAY sur le contenu principal, en secondes. | Fermeture du média | `a.media.timePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.timePlayed` |
| **[!UICONTROL Temps de lecture unique]** | Durée totale pendant laquelle le contenu unique est lu, en secondes. Cette mesure exclut la durée de lecture lors de l’affichage du contenu de répétition, comme la recherche vers l’arrière. | Fermeture du média | `a.media.`<br>`uniqueTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`uniqueTimePlayed` |
