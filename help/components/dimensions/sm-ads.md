---
title: Dimensions et services de streaming multimédia
description: Dimensions disponibles lorsque vous activez [!UICONTROL Publicités multimédia] pour une suite de rapports.
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 15%

---

# Dimensions et services de streaming multimédia

*Cette page décrit les dimensions disponibles lorsque vous activez [!UICONTROL Publicités multimédia] pour une suite de rapports. Voir [Mesures publicitaires des médias en flux continu](../metrics/sm-ads.md) pour connaître les mesures disponibles.*

Les dimensions et services Streaming Media fournissent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais des bibliothèques Streaming Media Services. L’utilisation de ces dimensions nécessite le module complémentaire **[!UICONTROL Adobe Analytics for Streaming Media]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Publicités multimédia]** sous [Rapports multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les dimensions suivantes sont disponibles :

| Nom de la dimension | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Publicité | Identifiant unique de la publicité. | Démarrage et fermeture de la publicité | `a.media.ad.name` |
| Nom de l’annonce publicitaire (variable) | Nom convivial de la publicité. Une dimension de classification nommée « Nom de l’annonce » est également disponible, dans un but similaire. Cette dimension et la classification sont traitées comme deux dimensions distinctes. | Démarrage et fermeture de la publicité | `a.media.ad.friendlyName` |
| Nom du lecteur publicitaire | Nom du lecteur qui effectue le rendu de la publicité. | Démarrage et fermeture de la publicité | `a.media.ad.playerName` |
| Longueur de l’annonce (variable) | Durée de la publicité vidéo, en secondes. | Démarrage et fermeture de la publicité | `a.media.ad.length` |
| Capsule publicitaire | Identifiant unique de la capsule publicitaire. | Démarrage et fermeture de la publicité | `a.media.ad.pod` |
| Position de l’annonce publicitaire dans la capsule | Position d’index de l’annonce publicitaire dans la coupure publicitaire parente (indexée sur 0). | Démarrage et fermeture de la publicité | `a.media.ad.podPosition` |
| Annonceur | Société ou marque présentée dans la publicité. | Démarrage et fermeture de la publicité | `a.media.ad.advertiser` |
| ID de campagne | ID de la campagne publicitaire | Démarrage et fermeture de la publicité | `a.media.ad.campaign` |

{style="table-layout:auto"}

En plus des dimensions ci-dessus, Adobe crée automatiquement les dimensions de classification suivantes. Vous devez charger des données de classification pour afficher les rapports qui utilisent ces dimensions.

| Nom de la classification | Dimension parente | Description |
| --- | --- | --- |
| ID de ressource | [Contenu](sm-core.md) | Identifiant unique du contenu de la ressource multimédia. Par exemple, l’identifiant de l’épisode de la série télévisée, l’identifiant de la ressource vidéo ou l’identifiant de l’événement en direct. Ces identifiants sont généralement dérivés d’autorités de métadonnées telles que EIDR, TMS/Gracenote, Rovi, ou d’autres systèmes propriétaires ou internes. |
| Classement du contenu | [Contenu](sm-core.md) | Évaluation telle que définie par les directives parentales TV. |
| Date de première diffusion | [Contenu](sm-core.md) | Date à laquelle le contenu a été diffusé à la télévision pour la première fois. Comme cette dimension de classification est une chaîne, tout format de date est autorisé. Adobe recommande d’utiliser un format de date cohérent, tel que `YYYY-MM-DD`. |
| Date de première distribution numérique | [Contenu](sm-core.md) | Date à laquelle le contenu a été diffusé pour la première fois sur une chaîne ou une plate-forme numérique. Comme cette dimension de classification est une chaîne, tout format de date est autorisé. Adobe recommande d’utiliser un format de date cohérent, tel que `YYYY-MM-DD`. |
| Longueur de la publicité | Publicité | Durée de la publicité vidéo, en secondes. |
| Nom de la publicité | Publicité | Nom convivial de la publicité. Il s’agit de l’équivalent de classification de « Nom de l’annonce (variable) ». |
| ID d’élément créatif | Publicité | Identifiant du contenu publicitaire. |
| Nom de la capsule | Capsule publicitaire | Nom convivial de la capsule publicitaire. |
| Position de la capsule | Capsule publicitaire | Décalage de la coupure publicitaire dans le contenu, en secondes. |

{style="table-layout:auto"}
