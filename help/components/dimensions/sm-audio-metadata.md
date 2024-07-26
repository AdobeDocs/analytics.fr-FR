---
title: Dimensions des métadonnées audio des médias en flux continu
description: Dimensions disponibles lorsque vous activez [!UICONTROL Métadonnées audio] pour une suite de rapports.
feature: Dimensions
source-git-commit: 45b371bd20223b86d0f17d9bdb48cffb2de15468
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 8%

---

# Dimensions des métadonnées audio des médias en flux continu

Les dimensions de publicité des médias en flux continu offrent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais de bibliothèques de collecte de médias en flux continu. L’utilisation de ces dimensions nécessite le **[!UICONTROL module complémentaire Adobe Streaming Media Collection]**. Pour plus d’informations, contactez votre équipe de compte d’Adobe.

Lorsque vous activez les **[!UICONTROL métadonnées audio]** sous [Rapports multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les dimensions suivantes sont disponibles :

| Nom de la dimension | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Album | Nom de l’album. | Démarrage du média, Fermeture du média | `a.media.album` |
| Artiste | Nom de l’artiste. | Démarrage du média, Fermeture du média | `a.media.artist` |
| Auteur | Nom de l’auteur du livre audio. | Démarrage du média, Fermeture du média | `a.media.author` |
| Étiquette | Nom du libellé de l’enregistrement. | Démarrage du média, Fermeture du média | `a.media.label` |
| Éditeur | Nom de l’éditeur de contenu audio. | Démarrage du média, Fermeture du média | `a.media.publisher` |
| Station | Nom ou identifiant de la station radio. | Démarrage du média, Fermeture du média | `a.media.station` |

{style="table-layout:auto"}
