---
title: Nom du robot
description: Nom du robot qui correspondait aux règles de robots.
exl-id: 668c1dce-c603-477a-9df7-dacb649bbf63
feature: Dimensions
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 7%

---

# Nom du robot

Le &quot;nom du robot&quot; [dimension](overview.md) affiche les noms des robots détectés à l’aide de [Règles de robots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md). Il peut s’agir de règles IAB par défaut ou de règles de robots personnalisées configurées par votre organisation. Il s’avère utile lorsque vous souhaitez en savoir plus sur les robots qui visitent votre site ou ceux qui génèrent le plus de trafic.

Accès qui correspondent [!UICONTROL Règles de robots] sont automatiquement filtrés hors de tous les rapports Analytics, à l’exception de cette dimension, [Occurrences du robot](../metrics/bot-occurrences.md), et [Pages vues de robots](../metrics/bot-page-views.md). Vous pouvez utiliser cette dimension et ces deux mesures pour déterminer quelles données de robots sont exclues du reste de vos rapports.

La création de rapports de robots étant séparée du reste des données de votre suite de rapports, seules les dimensions et mesures suivantes sont prises en charge avec cette dimension :

* [Page](page.md)
* Dimensions basées sur le temps (par exemple, [Jour](day.md), [Semaine](week.md), ou [Mois](month.md))
* [Occurrences du robot](../metrics/bot-occurrences.md)
* [Vues de page robot](../metrics/bot-page-views.md)

L’utilisation d’une autre dimension ou mesure avec cette dimension ne renvoie pas de données.

## Renseigner cette dimension avec des données

Si vous avez activé [Règles de robots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md), cette dimension collecte automatiquement les données. Si vous n’avez pas encore activé [!UICONTROL Règles de robots], cette dimension n’apparaît pas dans Analysis Workspace.

## Éléments de dimension

Chaque élément de dimension répertorie le nom du robot qui correspondait aux critères de règle de robot IAB ou personnalisé.
