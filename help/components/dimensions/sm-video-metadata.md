---
title: Dimensions des métadonnées vidéo de médias en flux continu
description: Dimensions disponibles lorsque vous activez les [!UICONTROL métadonnées vidéo] pour une suite de rapports.
feature: Dimensions
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 7%

---

# Dimensions des métadonnées vidéo de médias en flux continu

*Cette page décrit les dimensions disponibles lorsque vous activez les [!UICONTROL métadonnées vidéo] pour une suite de rapports. Voir [Mesures de métadonnées vidéo de média en flux continu](../metrics/sm-video-metadata.md) pour connaître les mesures disponibles.*

Les dimensions de publicité des médias en flux continu offrent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais de bibliothèques de collecte de médias en flux continu. L’utilisation de ces dimensions nécessite le **[!UICONTROL module complémentaire Adobe Streaming Media Collection]**. Pour plus d’informations, contactez votre équipe de compte d’Adobe.

Lorsque vous activez les **[!UICONTROL métadonnées vidéo]** sous [Rapports multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les dimensions suivantes sont disponibles :

| Nom de la dimension | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Chargements de publicité | Type de publicité chargée. | À confirmer | `a.media.adLoad` |
| Partie de la journée | Heure de la journée à laquelle le contenu a été diffusé ou lu. Toute valeur de chaîne est prise en charge. | Démarrage du média, Fermeture du média | `a.media.dayPart` |
| Épisode | Numéro de l’épisode. | Démarrage du média, Fermeture du média | `a.media.episode` |
| Type de flux multimédia | Type de flux. | Démarrage du média, Fermeture du média | `a.media.feed` |
| Genre | Type ou regroupement de contenu tel que défini par le producteur de contenu. Cette dimension prend en charge plusieurs valeurs, délimitées par des virgules. | Démarrage du média, Fermeture du média | `a.media.genre` |
| MVPD | Le MVPD fourni par l’authentification par Adobe. | Démarrage du média, Fermeture du média | `a.media.pass.mvpd` |
| Réseau | Nom du réseau ou du canal | Démarrage du média, Fermeture du média | `a.media.network` |
| Saison | Numéro de la saison auquel le programme appartient. | Démarrage du média, Fermeture du média | `a.media.season` |
| Programme | Nom du programme ou de la série. | Démarrage du média, Fermeture du média | `a.media.show` |
| Type de programme | Entier représentant le type de contenu.<br>`0` : épisode complet<br>`1` : aperçu ou bande-annonce<br>`2` : clip<br>`3` : autre | Démarrage du média, Fermeture du média | `a.media.type` |

{style="table-layout:auto"}
