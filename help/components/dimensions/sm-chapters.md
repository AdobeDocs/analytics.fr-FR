---
title: Dimensions du chapitre Média en flux continu
description: Dimensions disponibles lorsque vous activez [!UICONTROL Chapitres multimédia] pour une suite de rapports.
feature: Dimensions
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 14%

---

# Dimensions du chapitre Média en flux continu

*Cette page décrit les dimensions disponibles lorsque vous activez les [!UICONTROL Chapitres multimédia] pour une suite de rapports. Voir [Mesures de chapitre de médias en flux continu](../metrics/sm-chapters.md) pour connaître les mesures disponibles.*

Les dimensions de chapitre Média en flux continu offrent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais de bibliothèques de collecte de médias en flux continu. L’utilisation de ces dimensions nécessite le **[!UICONTROL module complémentaire Adobe Streaming Media Collection]**. Pour plus d’informations, contactez votre équipe de compte d’Adobe.

Lorsque vous activez les **[!UICONTROL Chapitres multimédia]** sous [Rapports multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), la dimension suivante est disponible :

| Nom de la dimension | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Chapitre | ID de chapitre généré automatiquement. | Fermeture du chapitre | `a.media.chapter.name` |

{style="table-layout:auto"}

Outre les dimensions ci-dessus, Adobe crée automatiquement les dimensions de classification suivantes. Vous devez télécharger des données de classification pour afficher les rapports qui utilisent ces dimensions.

| Nom de la classification | Dimension parente | Description |
| --- | --- | --- |
| Créateur | [Contenu](sm-core.md) | Créateur du contenu. |
| Durée du chapitre | Chapitre | Durée du chapitre, en secondes. |
| Nom du chapitre | Chapitre | Nom convivial du chapitre. |
| Décalage de chapitre | Chapitre | Décalage du chapitre dans le contenu à partir du début, en secondes. |
| Position du chapitre | Chapitre | Position de l’index du chapitre dans le contenu. |

{style="table-layout:auto"}
