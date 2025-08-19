---
title: Mesures de chapitre sur les services de streaming multimédia
description: Mesures disponibles lorsque vous activez [!UICONTROL Chapitres de médias] pour une suite de rapports.
feature: Metrics
exl-id: bef379d5-9dc9-404f-8197-1ba66d11299d
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 5%

---

# Mesures de chapitre sur les services de streaming multimédia

*Cette page décrit les mesures disponibles lorsque vous activez [!UICONTROL Chapitres multimédia] pour une suite de rapports. Voir [Dimensions du chapitre sur les services de streaming multimédia](../dimensions/sm-chapters.md) pour connaître les dimensions disponibles.*

Les mesures de chapitre sur les services de streaming multimédia fournissent des fonctionnalités de reporting supplémentaires à la collecte de données par le biais des bibliothèques de collecte de services de streaming multimédia. L’utilisation de ces mesures nécessite le module complémentaire **[!UICONTROL Adobe Analytics for Streaming Media]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Chapitres multimédia]** sous [Création de rapports multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les mesures suivantes sont disponibles :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Lectures complètes du chapitre | Valeur booléenne qui se déclenche à la fin d’un chapitre. | Fermeture du chapitre | `a.media.chapter.complete` |
| Démarrages du chapitre | Valeur booléenne qui se déclenche au début d’un chapitre. | Début du chapitre | `a.media.chapter.view` |
| Temps passé sur le chapitre | Temps passé sur le chapitre, en secondes. | Fermeture du chapitre | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}
