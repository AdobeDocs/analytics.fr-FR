---
title: Dimensions principales du streaming multimédia
description: Dimensions disponibles lorsque vous activez [!UICONTROL &#x200B; Media Core &#x200B;] pour une suite de rapports.
feature: Dimensions
exl-id: 1316a646-a31a-49a4-a670-d56d90dd462b
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 10%

---

# Dimensions principales du streaming multimédia

*Cette page décrit les dimensions disponibles lorsque vous activez [!UICONTROL &#x200B; Media Core] pour une suite de rapports. Voir [Mesures principales des médias en flux continu](../metrics/sm-core.md) pour connaître les mesures disponibles.*

Les dimensions principales Streaming Media fournissent une fonctionnalité de création de rapports de base aux données collectées via les bibliothèques de collecte de médias en flux continu. L’utilisation de ces dimensions nécessite la collection Streaming Media d’Adobe **&#x200B;**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Media Core]** sous [Rapports multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les dimensions suivantes sont disponibles :

| Nom de la dimension | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Contenu | Identifiant du contenu. | Début du média, Fermer le média | `a.media.name` |
| Canal de contenu | Station ou canal de distribution sur lequel le contenu est lu. Toute valeur de chaîne est valide. | Début du média, Fermer le média | `a.media.channel` |
| Longueur du contenu (variable) | Longueur maximale (ou durée) du contenu consommé, en secondes. Cette dimension est requise pour plusieurs mesures, y compris « Audience moyenne par minute ». Si cette dimension n’est pas définie, les mesures dépendantes ne sont pas disponibles.<br><br>Une dimension de classification nommée « Longueur de la vidéo » est également disponible, dans un but similaire. Cette dimension et la classification sont traitées comme deux dimensions distinctes. | Début du média, Fermer le média | `a.media.length` |
| Nom du contenu (variable) | Nom convivial du contenu. Une classification nommée « Nom de la vidéo » est également disponible, dans un but similaire. Cette dimension et la classification sont traitées comme deux dimensions distinctes. | Début du média, Fermer le média | `a.media.friendlyName` |
| Nom du lecteur de contenu | Nom du lecteur de contenu. | Début du média, Fermer le média | `a.media.playerName` |
| Segment de contenu | Intervalle qui décrit la partie du contenu qui a été visionnée, en minutes. Le segment correspond aux valeurs min. et max. du curseur de lecture au cours d’une session de lecture. | Fermeture du média | `a.media.segment` |
| Type de contenu | Type de contenu. Les valeurs valides sont les suivantes : `song`, `podcast`, `audiobook`, `radio`, `VoD`, `Live`, `Linear`, `UGC`, `DVoD` ou une valeur personnalisée. | Début du média, Fermer le média | `a.contentType` |
| Chemin du média | Chemin d’accès emprunté par le visiteur pour accéder au contenu. | Media Start | `a.media.path` |
| Type de diffusion | Type de diffusion. Les valeurs valides comprennent `audio` et `video`. | Début du média, Fermer le média | `a.media.streamType` |

{style="table-layout:auto"}

En plus des dimensions ci-dessus, Adobe crée automatiquement les dimensions de classification suivantes. Vous devez charger des données de classification pour afficher les rapports qui utilisent ces dimensions.

| Nom de la classification | Dimension parente | Description |
| --- | --- | --- |
| Durée de la vidéo | Contenu | Longueur maximale (ou durée) du contenu consommé, en secondes. Les mesures qui dépendent de la longueur du contenu ne peuvent pas utiliser cette classification. Vous devez créer une mesure calculée pour obtenir des mesures telles que « Audience moyenne par minute » à l’aide de cette classification. |
| Nom de la vidéo | Contenu | Nom convivial du contenu. Il s’agit de l’équivalent de classification de Nom du contenu (variable). |

{style="table-layout:auto"}
