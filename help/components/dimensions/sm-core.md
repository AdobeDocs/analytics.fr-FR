---
title: Dimensions de base des médias en flux continu
description: Dimensions disponibles lorsque vous activez [!UICONTROL Media Core] pour une suite de rapports.
feature: Dimensions
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 9%

---

# Dimensions de base des médias en flux continu

*Cette page décrit les dimensions disponibles lorsque vous activez [!UICONTROL Media Core] pour une suite de rapports. Voir [Mesures de base des médias en flux continu](../metrics/sm-core.md) pour connaître les mesures disponibles.*

Les dimensions de base des médias en flux continu offrent des fonctionnalités de création de rapports de base pour les données collectées au moyen de bibliothèques de collecte de médias en flux continu. L’utilisation de ces dimensions nécessite le **[!UICONTROL module complémentaire Adobe Streaming Media Collection]**. Pour plus d’informations, contactez votre équipe de compte d’Adobe.

Lorsque vous activez **[!UICONTROL Media Core]** sous [Media Reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les dimensions suivantes sont disponibles :

| Nom de la dimension | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Contenu | Identifiant du contenu. | Démarrage du média, Fermeture du média | `a.media.name` |
| Canal de contenu | La station ou le canal de distribution où le contenu est lu. Toute valeur de chaîne est valide. | Démarrage du média, Fermeture du média | `a.media.channel` |
| Durée du contenu (variable) | Durée (ou durée) maximale du contenu consommé, en secondes. Cette dimension est requise pour plusieurs mesures, y compris &quot;audience moyenne par minute&quot;. Si cette dimension n’est pas définie, les mesures dépendantes ne sont pas disponibles.<br><br>Une dimension de classification nommée &quot;Durée de la vidéo&quot; est également disponible, ce qui a un objectif similaire. Cette dimension et la classification sont traitées comme deux dimensions distinctes. | Démarrage du média, Fermeture du média | `a.media.length` |
| Nom du contenu (variable) | Nom convivial du contenu. Une classification nommée &quot;Nom de la vidéo&quot; est également disponible, ce qui fournit un objectif similaire. Cette dimension et la classification sont traitées comme deux dimensions distinctes. | Démarrage du média, Fermeture du média | `a.media.friendlyName` |
| Nom du lecteur de contenu | Nom du lecteur de contenu. | Démarrage du média, Fermeture du média | `a.media.playerName` |
| Segment de contenu | Intervalle qui décrit la partie du contenu visualisée, en minutes. Le segment correspond aux valeurs min. et max. du curseur de lecture au cours d’une session de lecture. | Fermeture du média | `a.media.segment` |
| Type de contenu | Type de contenu. Les valeurs valides sont `song`, `podcast`, `audiobook`, `radio`, `VoD`, `Live`, `Linear`, `UGC`, `DVoD` ou une valeur personnalisée. | Démarrage du média, Fermeture du média | `a.contentType` |
| Chemin du média | Chemin d’accès emprunté par le visiteur pour atteindre le contenu. | Démarrage du média | `a.media.path` |
| Type de diffusion | Type de diffusion. Les valeurs valides comprennent `audio` et `video`. | Démarrage du média, Fermeture du média | `a.media.streamType` |

{style="table-layout:auto"}

Outre les dimensions ci-dessus, Adobe crée automatiquement les dimensions de classification suivantes. Vous devez télécharger des données de classification pour afficher les rapports qui utilisent ces dimensions.

| Nom de la classification | Dimension parente | Description |
| --- | --- | --- |
| Durée de la vidéo | Contenu | Durée (ou durée) maximale du contenu consommé, en secondes. Les mesures qui dépendent de la longueur du contenu ne peuvent pas utiliser cette classification. Vous devez créer une mesure calculée pour obtenir des mesures telles que &quot;audience moyenne par minute&quot; à l’aide de cette classification. |
| Nom de la vidéo | Contenu | Nom convivial du contenu. Il s’agit de l’équivalent en termes de classification du nom de contenu (variable). |

{style="table-layout:auto"}
