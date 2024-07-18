---
title: Nom du robot
description: Nom du robot qui correspondait aux règles de robots.
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 7%

---

# Nom du robot

La [dimension](overview.md) du &quot;nom de robot&quot; indique le nom des robots détectés à l’aide des [règles de robots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md). Il peut s’agir de règles IAB par défaut ou de règles de robots personnalisées configurées par votre organisation. Il s’avère utile lorsque vous souhaitez en savoir plus sur les robots qui visitent votre site ou ceux qui génèrent le plus de trafic.

Les accès qui correspondent à [!UICONTROL Règles de robots] sont automatiquement filtrés de tous les rapports Analytics, à l’exception de cette dimension, des [occurrences de robots](../metrics/bot-occurrences.md) et des [pages vues de robots](../metrics/bot-page-views.md). Vous pouvez utiliser cette dimension et ces deux mesures pour déterminer quelles données de robots sont exclues du reste de vos rapports.

La création de rapports de robots étant séparée du reste des données de votre suite de rapports, seules les dimensions et mesures suivantes sont prises en charge avec cette dimension :

* [Page](page.md)
* Dimensions basées sur le temps (par exemple, [Jour](day.md), [Semaine](week.md) ou [Mois](month.md))
* [Occurrences du robot](../metrics/bot-occurrences.md)
* [Vues de page robot](../metrics/bot-page-views.md)

L’utilisation d’une autre dimension ou mesure avec cette dimension ne renvoie pas de données.

## Renseigner cette dimension avec des données

Si vous avez activé les [règles de robots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md), cette dimension collecte automatiquement les données. Si vous n’avez pas encore activé les [!UICONTROL règles de robots], cette dimension n’apparaît pas dans Analysis Workspace.

## Éléments de dimension

Chaque élément de dimension répertorie le nom du robot qui correspondait aux critères de règle de robot IAB ou personnalisé.
