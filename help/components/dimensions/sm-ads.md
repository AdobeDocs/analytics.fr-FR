---
title: Dimensions et médias en flux continu
description: Dimensions disponibles lorsque vous activez [!UICONTROL Media Ads] pour une suite de rapports.
feature: Dimensions
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 15%

---

# Dimensions et médias en flux continu

*Cette page décrit les dimensions disponibles lorsque vous activez [!UICONTROL Media Ads] pour une suite de rapports. Voir [Mesures publicitaires de médias en flux continu](../metrics/sm-ads.md) pour connaître les mesures disponibles.*

Les dimensions de publicité des médias en flux continu offrent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais de bibliothèques de collecte de médias en flux continu. L’utilisation de ces dimensions nécessite le **[!UICONTROL module complémentaire Adobe Streaming Media Collection]**. Pour plus d’informations, contactez votre équipe de compte d’Adobe.

Lorsque vous activez **[!UICONTROL Media Ads]** sous [Media reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les dimensions suivantes sont disponibles :

| Nom de la dimension | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Publicité | Identifiant unique de la publicité. | Démarrage de publicité, Fermeture de publicité | `a.media.ad.name` |
| Nom de la publicité (variable) | Nom convivial de la publicité. Une dimension de classification nommée &quot;Nom de la publicité&quot; est également disponible, ce qui a un objectif similaire. Cette dimension et la classification sont traitées comme deux dimensions distinctes. | Démarrage de publicité, Fermeture de publicité | `a.media.ad.friendlyName` |
| Nom du lecteur publicitaire | Nom du lecteur qui effectue le rendu de la publicité. | Démarrage de publicité, Fermeture de publicité | `a.media.ad.playerName` |
| Longueur de la publicité (variable) | Durée de la publicité vidéo, en secondes. | Démarrage de publicité, Fermeture de publicité | `a.media.ad.length` |
| Capsule publicitaire | Identifiant unique de la capsule publicitaire. | Démarrage de publicité, Fermeture de publicité | `a.media.ad.pod` |
| Position de la publicité dans la capsule | Position de l’index de la publicité dans la coupure publicitaire parente (indexée 0). | Démarrage de publicité, Fermeture de publicité | `a.media.ad.podPosition` |
| Annonceur | Entreprise ou marque apparue dans la publicité. | Démarrage de publicité, Fermeture de publicité | `a.media.ad.advertiser` |
| ID de campagne | ID de la campagne publicitaire | Démarrage de publicité, Fermeture de publicité | `a.media.ad.campaign` |

{style="table-layout:auto"}

Outre les dimensions ci-dessus, Adobe crée automatiquement les dimensions de classification suivantes. Vous devez télécharger des données de classification pour afficher les rapports qui utilisent ces dimensions.

| Nom de la classification | Dimension parente | Description |
| --- | --- | --- |
| ID de ressource | [Contenu](sm-core.md) | Identifiant unique du contenu de la ressource multimédia. Par exemple, l’identifiant d’épisode de la série télévisée, l’identifiant de ressource de film ou l’identifiant d’événement en direct. Ces identifiants sont généralement dérivés des autorités de métadonnées telles que EIDR, TMS/Gracenote, Rovi ou d’autres systèmes propriétaires ou internes. |
| Évaluation du contenu | [Contenu](sm-core.md) | Évaluation telle que définie par les directives parentales de la télévision. |
| Date de première diffusion | [Contenu](sm-core.md) | Date à laquelle le contenu a été diffusé à la télévision pour la première fois. Puisque cette dimension de classification est une chaîne, tout format de date est autorisé. Adobe recommande d’utiliser un format de date cohérent, tel que `YYYY-MM-DD`. |
| Date de première distribution numérique | [Contenu](sm-core.md) | Date à laquelle le contenu a été diffusé pour la première fois sur une chaîne ou une plate-forme numérique. Puisque cette dimension de classification est une chaîne, tout format de date est autorisé. Adobe recommande d’utiliser un format de date cohérent, tel que `YYYY-MM-DD`. |
| Longueur de la publicité | Publicité | Durée de la publicité vidéo, en secondes. |
| Nom de la publicité | Publicité | Nom convivial de la publicité. Il s’agit de l’équivalent en termes de classification de &quot;Nom de la publicité (variable)&quot;. |
| ID d’élément créatif | Publicité | Identifiant de l’élément créatif publicitaire. |
| Nom de la capsule | Capsule publicitaire | Nom convivial de la capsule publicitaire. |
| Position de la capsule | Capsule publicitaire | Décalage de la coupure publicitaire dans le contenu, en secondes. |

{style="table-layout:auto"}
