---
title: Prise en charge des cookies
description: Détermine si le navigateur prend en charge les cookies.
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
TQID: https://experienceleague.adobe.com/axOR-Ut8kkRSCTYPescoSCa44g25E8xxp4gg-yQlyYw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 92%

---

# Prise en charge des cookies

La [dimension](overview.md) « Prise en charge des cookies » indique si le navigateur prend en charge les cookies pour un accès donné. Elle est utile pour déterminer le ratio de visiteurs qui utilisent des navigateurs prenant en charge les cookies et ceux qui les désactivent intentionnellement.

## Renseignement de cette dimension avec des données

Cette dimension collecte les données de la [`k`chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement tente de définir un cookie nommé `s_cc`, puis détecte si le cookie existe. Le résultat est la valeur du paramètre de chaîne de requête `Y` (si le navigateur prend en charge les cookies et qu’ils sont activés) ou `N` (si les cookies sont désactivés dans le navigateur). Si vous utilisez AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (via l’API, par exemple), veillez à inclure le paramètre de chaîne de requête `k` sur chaque accès avec la valeur `Y` ou `N`.

## Éléments de dimension

Les éléments de dimension comprennent `Enabled`, `Disabled` et `Unknown`.

* **`Enabled`** : le navigateur prend en charge les cookies et ils sont activés.
* **`Disabled`** : le navigateur ne prend pas en charge les cookies ou le visiteur les a désactivés.
* **`Unknown`** : AppMeasurement n’a pas pu déterminer la prise en charge des cookies. La chaîne de requête `k` n’était pas présente dans la demande d’image.
