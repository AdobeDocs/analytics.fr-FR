---
title: Profondeur de couleur
description: Profondeur de couleur de l’appareil.
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
TQID: https://experienceleague.adobe.com/JLxm06wch2r7RslhdKx-gFLBLhMSXuWkb-0EYM7nT5s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 94%

---

# Profondeur de couleur

La [dimension](overview.md) « Profondeur des couleurs » indique le nombre de couleurs prises en charge par l’appareil. Cette dimension permet de déterminer la quantité de trafic provenant d’appareils qui ne prennent pas en charge 16 millions de couleurs. Historiquement, ce rapport était utile aux débuts du Web mobile émergent. Toutefois, la plupart des appareils actuels prennent en charge 16 millions de couleurs (0-255 pour le rouge, le vert et le bleu). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche, convertissant la valeur en bits en un format plus lisible. Elle collecte les données de la [`c` chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement utilise la variable `screen.colorDepth` pour renseigner la chaîne de requête de demande d’image. Si vous utilisez AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (via l’API, par exemple), veillez à inclure le paramètre de chaîne de requête `c` sur chaque accès avec une valeur en bits valide.

## Éléments de dimension

Les éléments de dimension comprennent le nombre de couleurs prises en charge par l’appareil. Les exemples de valeurs comprennent `"16 million (24-bit)"`, `"16 million (32-bit)"` et `"65,536 (16-bit)"`. Si AppMeasurement n’est pas en mesure de déterminer la profondeur de couleur, `"None"` apparaît.

>[!TIP]
>
>La différence entre la prise en charge 24 bits et 32 bits est que la version 32 bits prend en charge un canal Alpha (RVBA), alors que la version 24 bits ne le fait pas (RVB). Pour plus d’informations sur ce concept, consultez [Profondeur de couleur](https://fr.wikipedia.org/wiki/Profondeur_de_couleur_(informatique)) sur Wikipédia.
