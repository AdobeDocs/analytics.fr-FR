---
title: Profondeur de couleur
description: Profondeur de couleur de l’appareil.
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
TQID: https://experienceleague.adobe.com/JLxm06wch2r7RslhdKx-gFLBLhMSXuWkb-0EYM7nT5s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 52%
---
# Profondeur de couleur

La [dimension](overview.md) « Profondeur des couleurs » indique le nombre de couleurs prises en charge par l’appareil. Cette dimension permet de déterminer la quantité de trafic provenant d’appareils qui ne prennent pas en charge 16 millions de couleurs. Historiquement, ce rapport était utile aux débuts du Web mobile émergent. Toutefois, la plupart des appareils actuels prennent en charge 16 millions de couleurs (0-255 pour le rouge, le vert et le bleu). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Renseignement de cette dimension avec des données

La profondeur de couleur est collectée automatiquement, côté client, à partir de la propriété `screen.colorDepth` du navigateur, qu’Adobe traduit par une table de recherche dans un format lisible. Elle est prête à l’emploi dans toute implémentation d’AppMeasurement ou de Web SDK (balises). Il n’y a aucune variable à définir. Si vous collectez des données en dehors d’AppMeasurement ou de Web SDK (par exemple via l’API), envoyez une valeur de bit valide sur chaque accès.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (collecté automatiquement) |
| **Champ Web SDK/XDM** | Aucun (collecté automatiquement) |
| **Paramètre de requête** | [`c`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<colorDepth>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | 20 octets |
| **Persistance** | S.O. |

## Éléments de dimension

Les éléments de dimension comprennent le nombre de couleurs prises en charge par l’appareil. Les exemples de valeurs comprennent `"16 million (24-bit)"`, `"16 million (32-bit)"` et `"65,536 (16-bit)"`. Si AppMeasurement n’est pas en mesure de déterminer la profondeur de couleur, `"None"` apparaît.

>[!TIP]
>
>La différence entre la prise en charge 24 bits et 32 bits est que la version 32 bits prend en charge un canal Alpha (RVBA), alors que la version 24 bits ne le fait pas (RVB). Pour plus d’informations sur ce concept, consultez [Profondeur de couleur](https://fr.wikipedia.org/wiki/Profondeur_de_couleur_(informatique)) sur Wikipédia.
