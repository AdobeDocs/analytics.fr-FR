---
title: Mesures principales des services de streaming multimédia
description: Mesures disponibles lorsque vous activez [!UICONTROL  Media Core ] pour une suite de rapports.
feature: Metrics
exl-id: f4ff5f84-18b6-4e67-b808-133faeaf8605
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 1%

---

# Mesures principales des services de streaming multimédia

*Cette page décrit les mesures disponibles lorsque vous activez [!UICONTROL Media Core] pour une suite de rapports. Consultez [Dimensions principales des services de streaming multimédia](../dimensions/sm-core.md) pour connaître les dimensions disponibles.*

Les mesures principales des services de streaming multimédia fournissent une fonctionnalité de création de rapports de base aux données collectées via les bibliothèques de collecte des services de streaming multimédia. L’utilisation de ces mesures nécessite le module complémentaire **[!UICONTROL Adobe Analytics for Streaming Media]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Media Core]** sous [Rapports multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les mesures suivantes sont disponibles :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Audience moyenne par minute | Temps total passé sur un élément de contenu donné, divisé par sa durée pour toutes ses sessions de lecture.<br>`[Time spent] / [Media length]` | Fermeture du média | `a.media.averageMinuteAudience` |
| Content completes | Se déclenche lorsqu’un élément de contenu se termine. Cette mesure ne signifie pas nécessairement qu’ils ont consulté l’intégralité du contenu ; ils auraient pu l’ignorer. Cela signifie uniquement qu’ils ont atteint la fin du contenu. | `a.media.complete` |
| Flux impactés en pause | Valeur booléenne qui se déclenche si une ou plusieurs pauses se sont produites pendant la lecture du contenu. | Fermeture du média | `a.media.pause` |
| Événements Pause | Nombre de pauses survenues au cours d’une session de lecture. | Fermeture du média | `a.media.pauseCount` |
| Durée totale de la pause | Durée totale de tous les événements de pause, en secondes. | Fermeture du média | `a.media.pauseTime` |
| Le contenu démarre | La première image du média est consommée. Si un utilisateur ou une utilisatrice tombe pendant une publicité ou pendant la mise en mémoire tampon, cet événement ne se déclenche pas. | Fermeture du média | `a.media.play` |
| Marque de progression de 10 % | Le curseur de lecture transmet le marqueur de 10 % du contenu en fonction de la longueur. Ce marqueur n’est comptabilisé qu’une seule fois, même si la recherche est effectuée à rebours. Si vous effectuez une recherche vers l’avant, les marqueurs ignorés ne sont pas comptabilisés. | Fermeture du média | `a.media.progress10` |
| Marque de progression de 25 % | Le curseur de lecture transmet le marqueur de 25 % du contenu en fonction de la longueur. Ce marqueur n’est comptabilisé qu’une seule fois, même si la recherche est effectuée à rebours. Si vous effectuez une recherche vers l’avant, les marqueurs ignorés ne sont pas comptabilisés. | Fermeture du média | `a.media.progress25` |
| Marqueur de progression de 50 % | Le curseur de lecture transmet le marqueur de 50 % du contenu en fonction de la longueur. Ce marqueur n’est comptabilisé qu’une seule fois, même si la recherche est effectuée à rebours. Si vous effectuez une recherche vers l’avant, les marqueurs ignorés ne sont pas comptabilisés. | Fermeture du média | `a.media.progress50` |
| Marqueur de progression de 75 % | Le curseur de lecture franchit le marqueur de 75 % du contenu en fonction de la longueur. Ce marqueur n’est comptabilisé qu’une seule fois, même si la recherche est effectuée à rebours. Si vous effectuez une recherche vers l’avant, les marqueurs ignorés ne sont pas comptabilisés. | Fermeture du média | `a.media.progress75` |
| Marque de progression de 95 % | Le curseur de lecture transmet le marqueur de 95 % du contenu en fonction de la longueur. Ce marqueur n’est comptabilisé qu’une seule fois, même si la recherche est effectuée à rebours. Si vous effectuez une recherche vers l’avant, les marqueurs ignorés ne sont pas comptabilisés. | Fermeture du média | `a.media.progress95` |
| Reprises du contenu | Valeur booléenne qui se déclenche lorsque le contenu est repris après une période de plus de 30 minutes de mise en tampon, de pause ou de blocage. Se déclenche également si le lecteur le définit sur le trackPlay VideoInfo. | Fermeture du média | `a.media.resume` |
| Vues de segment de contenu | Valeur booléenne qui se déclenche sur la première image du segment affiché. | Fermeture du média | `a.media.segmentView` |
| Démarrages du média | Valeur booléenne qui se déclenche lors du chargement initial du média. Cet événement inclut les publicités, la mise en mémoire tampon et les erreurs. | Media Start | `a.media.view` |
| Durée du contenu | Durée totale des événements de type PLAY sur le contenu principal, en secondes. | Fermeture du média | `a.media.timePlayed` |
| Durée de lecture unique | Durée totale pendant laquelle le contenu unique est lu, en secondes. Cette mesure exclut la durée de lecture lors de l’affichage du contenu de répétition, comme la recherche vers l’arrière. | Fermeture du média | `a.media.uniqueTimePlayed` |

{style="table-layout:auto"}
