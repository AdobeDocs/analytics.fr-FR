---
title: Nom du robot
description: Nom du robot qui correspondait aux règles de robots.
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
TQID: https://experienceleague.adobe.com/lJn65s1JtcJf7WobPEeouvwlk7G5qd8XtgxvGLY-zu8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 218
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
