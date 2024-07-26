---
title: Mesures de base des médias en flux continu
description: Mesures disponibles lorsque vous activez [!UICONTROL Media Core] pour une suite de rapports.
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 1%

---

# Mesures de base des médias en flux continu

*Cette page décrit les mesures disponibles lorsque vous activez [!UICONTROL Media Core] pour une suite de rapports. Voir [Dimensions de base des médias en flux continu](../dimensions/sm-core.md) pour connaître les dimensions disponibles.*

Les mesures de base des médias en flux continu offrent des fonctionnalités de création de rapports de base pour les données collectées au moyen des bibliothèques de collecte de médias en flux continu. L’utilisation de ces mesures nécessite le **[!UICONTROL module complémentaire Adobe de collecte de médias en flux continu]**. Pour plus d’informations, contactez votre équipe de compte d’Adobe.

Lorsque vous activez **[!UICONTROL Media Core]** sous [Rapport multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les mesures suivantes sont disponibles :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Audience par minute moyenne | Durée totale passée sur un élément de contenu donné, divisée par la durée de ce contenu pour l’ensemble de ses sessions de lecture.<br>`[Time spent] / [Media length]` | Fermeture du média | `a.media.averageMinuteAudience` |
| Contenu terminé | Se déclenche lorsqu’un élément de contenu se termine. Cette mesure ne signifie pas nécessairement qu’ils ont consulté l’intégralité du contenu ; ils auraient pu passer au début. Cela signifie uniquement qu’ils ont atteint la fin du contenu. | `a.media.complete` |
| Flux touchés en pause | Valeur booléenne qui se déclenche si une ou plusieurs pauses se produisent pendant la lecture du contenu. | Fermeture du média | `a.media.pause` |
| Événements de mise en pause | Nombre de pauses survenues au cours d’une session de lecture. | Fermeture du média | `a.media.pauseCount` |
| Durée totale de mise en pause | Durée totale de tous les événements de pause, en secondes. | Fermeture du média | `a.media.pauseTime` |
| Démarrages de contenu | La première image du média est visionnée. Si un utilisateur abandonne pendant une publicité ou pendant la mise en mémoire tampon, cet événement ne se déclenche pas. | Fermeture du média | `a.media.play` |
| Marqueur de progression de 10 % | Le curseur de lecture passe le marqueur de 10 % du contenu en fonction de la durée. Ce marqueur n’est compté qu’une seule fois, même si vous effectuez une recherche vers l’arrière. Si vous effectuez une recherche vers l’avant, les marqueurs ignorés ne sont pas comptabilisés. | Fermeture du média | `a.media.progress10` |
| Marqueur de progression de 25 % | Le curseur de lecture passe le marqueur de 25 % du contenu en fonction de la durée. Ce marqueur n’est compté qu’une seule fois, même si vous effectuez une recherche vers l’arrière. Si vous effectuez une recherche vers l’avant, les marqueurs ignorés ne sont pas comptabilisés. | Fermeture du média | `a.media.progress25` |
| Marqueur de progression de 50 % | Le curseur de lecture passe le marqueur de 50 % du contenu en fonction de la durée. Ce marqueur n’est compté qu’une seule fois, même si vous effectuez une recherche vers l’arrière. Si vous effectuez une recherche vers l’avant, les marqueurs ignorés ne sont pas comptabilisés. | Fermeture du média | `a.media.progress50` |
| Marqueur de progression de 75 % | Le curseur de lecture passe le marqueur de 75 % du contenu en fonction de la durée. Ce marqueur n’est compté qu’une seule fois, même si vous effectuez une recherche vers l’arrière. Si vous effectuez une recherche vers l’avant, les marqueurs ignorés ne sont pas comptabilisés. | Fermeture du média | `a.media.progress75` |
| Marqueur de progression de 95 % | Le curseur de lecture passe le marqueur de 95 % du contenu en fonction de la durée. Ce marqueur n’est compté qu’une seule fois, même si vous effectuez une recherche vers l’arrière. Si vous effectuez une recherche vers l’avant, les marqueurs ignorés ne sont pas comptabilisés. | Fermeture du média | `a.media.progress95` |
| Le contenu reprend | Valeur booléenne qui se déclenche lorsque le contenu reprend après plus de 30 minutes de mise en mémoire tampon, de mise en pause ou de blocage. Se déclenche également s’il est défini par le lecteur sur VideoInfo trackPlay. | Fermeture du média | `a.media.resume` |
| Affichages de segments de contenu | Valeur booléenne qui se déclenche sur la première image du segment consulté. | Fermeture du média | `a.media.segmentView` |
| Démarrages de média | Valeur booléenne qui se déclenche lors du chargement initial du média. Cet événement comprend des publicités, des mises en mémoire tampon et des erreurs. | Démarrage du média | `a.media.view` |
| Temps passé sur le contenu | Durée totale de l’événement pour tous les événements de type LECTURE sur le contenu principal, en secondes. | Fermeture du média | `a.media.timePlayed` |
| Durée de lecture unique | Durée totale de lecture du contenu unique, en secondes. Cette mesure exclut la durée de lecture lors de l’affichage du contenu répété, telle que la recherche vers l’arrière. | Fermeture du média | `a.media.uniqueTimePlayed` |

{style="table-layout:auto"}
