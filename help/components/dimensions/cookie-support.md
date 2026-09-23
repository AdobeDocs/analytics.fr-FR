---
title: Prise en charge des cookies
description: Détermine si le navigateur prend en charge les cookies.
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
TQID: https://experienceleague.adobe.com/axOR-Ut8kkRSCTYPescoSCa44g25E8xxp4gg-yQlyYw
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
source-wordcount: '211'
ht-degree: 38%
---
# Prise en charge des cookies

La [dimension](overview.md) « Prise en charge des cookies » indique si le navigateur prend en charge les cookies pour un accès donné. Elle est utile pour déterminer la proportion de visiteurs qui utilisent un navigateur prenant en charge les cookies par rapport à ceux qui les désactivent volontairement

## Renseignement de cette dimension avec des données

La prise en charge des cookies est collectée automatiquement, côté client : AppMeasurement tente de définir un cookie nommé `s_cc`, puis indique s’il existe, `Y` si le navigateur prend en charge et a activé les cookies, ou `N` si les cookies sont désactivés. Elle est prête à l’emploi dans toute implémentation d’AppMeasurement ou de Web SDK (balises). Il n’y a aucune variable à définir. Si vous collectez des données en dehors d’AppMeasurement ou de Web SDK (par exemple via l’API), envoyez des `Y` ou des `N` sur chaque accès.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (collecté automatiquement) |
| **Champ Web SDK/XDM** | Aucun (collecté automatiquement) |
| **Paramètre de requête** | [`k`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<cookiesEnabled>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | 1 octet |
| **Persistance** | S.O. |

## Éléments de dimension

Les éléments de dimension comprennent `Enabled`, `Disabled` et `Unknown`.

* **`Enabled`** : le navigateur prend en charge les cookies et ils sont activés.
* **`Disabled`** : le navigateur ne prend pas en charge les cookies ou le visiteur les a désactivés.
* **`Unknown`** : AppMeasurement n’a pas pu déterminer la prise en charge des cookies. La chaîne de requête `k` n’était pas présente dans la demande d’image.
