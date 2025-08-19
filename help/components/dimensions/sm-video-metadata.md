---
title: Dimensions des métadonnées vidéo des services de streaming multimédia
description: Dimensions disponibles lorsque vous activez [!UICONTROL  Métadonnées vidéo ] pour une suite de rapports.
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 6%

---

# Dimensions des métadonnées vidéo des services de streaming multimédia

*Cette page décrit les dimensions disponibles lorsque vous activez [!UICONTROL Métadonnées vidéo] pour une suite de rapports. Voir [Mesures de métadonnées vidéo des services de streaming multimédia](../metrics/sm-video-metadata.md) pour connaître les mesures disponibles.*

Les dimensions et services de streaming multimédia fournissent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais des bibliothèques de collecte de services de streaming multimédia. L’utilisation de ces dimensions nécessite le module complémentaire **[!UICONTROL Adobe Analytics for Streaming Media]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Métadonnées vidéo]** sous [Rapports multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les dimensions suivantes sont disponibles :

| Nom de la dimension | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Chargements des annonces publicitaires | Type d’annonce publicitaire chargée. | À confirmer | `a.media.adLoad` |
| Partie de la journée | Heure de la journée à laquelle le contenu a été diffusé ou lu. Toute valeur de chaîne est prise en charge. | Début du média, Fermer le média | `a.media.dayPart` |
| Épisode | Numéro de l’épisode. | Début du média, Fermer le média | `a.media.episode` |
| Type de flux multimédia | Type de flux. | Début du média, Fermer le média | `a.media.feed` |
| Genre | Type ou groupement de contenu, tel que défini par le producteur du contenu. Cette dimension prend en charge plusieurs valeurs, délimitées par des virgules. | Début du média, Fermer le média | `a.media.genre` |
| MVPD | Le MVPD fourni par l’authentification Adobe. | Début du média, Fermer le média | `a.media.pass.mvpd` |
| Réseau | Nom du réseau ou du canal | Début du média, Fermer le média | `a.media.network` |
| Saison | Numéro de la saison à laquelle appartient l’émission. | Début du média, Fermer le média | `a.media.season` |
| Programme | Nom du programme ou de la série. | Début du média, Fermer le média | `a.media.show` |
| Type de programme | Nombre entier qui représente le type de contenu.<br>`0` : Épisode complet <br>`1` : Prévisualisation ou bande-annonce<br>`2` : Clip<br>`3` : Autre | Début du média, Fermer le média | `a.media.type` |

{style="table-layout:auto"}
