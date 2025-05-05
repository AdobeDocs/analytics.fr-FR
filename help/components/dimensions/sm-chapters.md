---
title: Dimensions des chapitres du streaming multimédia
description: Dimensions disponibles lorsque vous activez [!UICONTROL Chapitres de médias] pour une suite de rapports.
feature: Dimensions
exl-id: cac66a0b-3f83-46a9-b35c-ba08e0eafb92
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 14%

---

# Dimensions des chapitres du streaming multimédia

*Cette page décrit les dimensions disponibles lorsque vous activez [!UICONTROL Chapitres de média] pour une suite de rapports. Voir [Mesures du chapitre sur les médias en flux continu](../metrics/sm-chapters.md) pour connaître les mesures disponibles.*

Les dimensions de chapitre Streaming Media fournissent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais des bibliothèques de collecte de médias en flux continu. L’utilisation de ces dimensions nécessite la collection Streaming Media d’Adobe **&#x200B;**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Chapitres multimédia]** sous [Compte rendu des performances multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), la dimension suivante est disponible :

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
