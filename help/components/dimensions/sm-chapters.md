---
title: Dimensions des chapitres du streaming multimédia
description: Dimensions disponibles lorsque vous activez [!UICONTROL Chapitres de médias] pour une suite de rapports.
feature: Dimensions
exl-id: cac66a0b-3f83-46a9-b35c-ba08e0eafb92
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 13%

---

# Dimensions des chapitres des services de streaming multimédia

*Cette page décrit les dimensions disponibles lorsque vous activez [!UICONTROL Chapitres de média] pour une suite de rapports. Voir [Mesures du chapitre sur les services de streaming multimédia](../metrics/sm-chapters.md) pour connaître les mesures disponibles.*

Les dimensions de chapitre Services de streaming multimédia fournissent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais des bibliothèques de services de streaming multimédia. L’utilisation de ces dimensions nécessite le module complémentaire **[!UICONTROL Adobe Analytics for Streaming Media]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Chapitres multimédia]** sous [Compte rendu des performances multimédia](/help/admin/tools/manage-rs/edit-settings/media-management.md), la dimension suivante est disponible :

| Nom de la dimension | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Chapitre | Identifiant de chapitre généré automatiquement. | Fermeture du chapitre | `a.media.chapter.name` |

{style="table-layout:auto"}

En plus des dimensions ci-dessus, Adobe crée automatiquement les dimensions de classification suivantes. Vous devez charger des données de classification pour afficher les rapports qui utilisent ces dimensions.

| Nom de la classification | Dimension parente | Description |
| --- | --- | --- |
| Créateur | [Contenu](sm-core.md) | Créateur du contenu. |
| Durée du chapitre | Chapitre | Durée du chapitre, en secondes. |
| Nom du chapitre | Chapitre | Nom convivial du chapitre. |
| Décalage de chapitre | Chapitre | Décalage du chapitre à l’intérieur du contenu depuis le début, en secondes. |
| Position du chapitre | Chapitre | Position d’index du chapitre dans le contenu. |

{style="table-layout:auto"}
