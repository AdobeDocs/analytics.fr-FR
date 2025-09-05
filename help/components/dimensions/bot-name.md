---
title: Nom du robot
description: Nom du robot qui correspondait aux règles de robots.
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 7%

---

# Nom du robot

La [dimension](overview.md) « Nom des robots » affiche les noms des robots détectés à l’aide de [Règles de robots](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md). Ces règles peuvent être des règles IAB par défaut ou des règles de robots personnalisées que votre organisation configure. Cela s’avère utile lorsque vous souhaitez en savoir plus sur les robots qui visitent votre site ou sur ceux qui génèrent le plus de trafic.

Les accès qui correspondent à [!UICONTROL Règles de robots] sont automatiquement exclus de tous les rapports Analytics, à l’exception de cette dimension, [Occurrences de robots](../metrics/bot-occurrences.md) et [Pages vues de robots](../metrics/bot-page-views.md). Vous pouvez utiliser cette dimension et ces deux mesures pour voir quelles données de robots sont exclues du reste de vos rapports.

Comme les rapports sur les robots sont séparés du reste des données de votre suite de rapports, seules les dimensions et mesures suivantes sont prises en charge avec cette dimension :

* [Page](page.md)
* Dimensions temporelles (par exemple, [Jour](day.md), [Semaine](week.md) ou [Mois](month.md))
* [Occurrences du robot](../metrics/bot-occurrences.md)
* [Vues de page robot](../metrics/bot-page-views.md)

L’utilisation d’une autre dimension ou mesure avec cette dimension ne renvoie pas de données.

## Renseigner cette dimension avec des données

Si vous avez activé [Règles de robots](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md), cette dimension collecte automatiquement des données. Si vous n’avez pas encore activé [!UICONTROL Règles de robots], cette dimension n’apparaît pas dans Analysis Workspace.

## Éléments de dimension

Chaque élément de dimension répertorie le nom du robot correspondant aux critères IAB ou de règle de robot personnalisée.
