---
title: Mesures de chapitre sur le streaming multimédia
description: Mesures disponibles lorsque vous activez [!UICONTROL Chapitres de médias] pour une suite de rapports.
feature: Metrics
exl-id: bef379d5-9dc9-404f-8197-1ba66d11299d
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 5%

---

# Mesures de chapitre sur le streaming multimédia

*Cette page décrit les mesures disponibles lorsque vous activez [!UICONTROL Chapitres multimédia] pour une suite de rapports. Voir [Dimensions du chapitre Streaming Media](../dimensions/sm-chapters.md) pour connaître les dimensions disponibles.*

Les mesures de chapitre sur les médias en flux continu fournissent des fonctionnalités de création de rapports supplémentaires à la collecte de données par le biais des bibliothèques de collecte de médias en flux continu. L’utilisation de ces mesures nécessite la **[!UICONTROL collection Streaming Media Adobe]**. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.

Lorsque vous activez **[!UICONTROL Chapitres multimédia]** sous [Création de rapports multimédia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), les mesures suivantes sont disponibles :

| Nom de la mesure | Description | Envoyé avec | Variable de données contextuelles |
| --- | --- | --- | --- |
| Lectures complètes du chapitre | Valeur booléenne qui se déclenche à la fin d’un chapitre. | Fermeture du chapitre | `a.media.chapter.complete` |
| Démarrages du chapitre | Valeur booléenne qui se déclenche au début d’un chapitre. | Début du chapitre | `a.media.chapter.view` |
| Temps passé sur le chapitre | Temps passé sur le chapitre, en secondes. | Fermeture du chapitre | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}
