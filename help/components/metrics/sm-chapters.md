---
title: Mesures de chapitre des médias en flux continu
description: Mesures disponibles lorsque vous activez [!UICONTROL Chapitres multimédia] pour une suite de rapports.
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 5%

---

# Mesures de chapitre des médias en flux continu

*Cette page décrit les mesures disponibles lorsque vous activez les [!UICONTROL Chapitres multimédia] pour une suite de rapports. Voir [Dimensions du chapitre Média en flux continu](../dimensions/sm-chapters.md) pour connaître les dimensions disponibles.*

Les mesures de chapitre Média en flux continu offrent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais de bibliothèques de collecte de médias en flux continu. L’utilisation de ces mesures nécessite le **[!UICONTROL module complémentaire Adobe de collecte de médias en flux continu]**. Pour plus d’informations, contactez votre équipe de compte d’Adobe.

Lorsque vous activez les **[!UICONTROL Chapitres multimédia]** sous [Rapports multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les mesures suivantes sont disponibles :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Fin du chapitre | Valeur booléenne qui se déclenche à la fin d’un chapitre. | Fermeture du chapitre | `a.media.chapter.complete` |
| Démarrages de chapitre | Valeur booléenne qui se déclenche au début d’un chapitre. | Début du chapitre | `a.media.chapter.view` |
| Durée du chapitre | Durée du chapitre, en secondes. | Fermeture du chapitre | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}
