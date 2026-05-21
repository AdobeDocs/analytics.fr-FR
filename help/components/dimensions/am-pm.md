---
title: Matin/après-midi
description: Détermine si l’accès s’est produit le matin ou l’après-midi.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
TQID: https://experienceleague.adobe.com/R1syrJ7ylIe2ywH1isX4sjR2O84-8eL-jooYhjUdKhI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 121
ht-degree: 64%

---

# Matin/après-midi

La [dimension](overview.md) « matin/après-midi » fournit insight si l’accès s’est produit aux heures du matin ou de l’après-midi. L’heure de l’accès est basée sur le [fuseau horaire de la suite de rapports](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi. Elle ne comporte aucun paramètre à modifier. Sa seule dépendance concerne le fuseau horaire de la suite de rapports, qui détermine les heures du matin et celles de l’après-midi.

## Éléments de dimension

Cette dimension contient toujours exactement deux éléments de dimension : `"AM"` et `"PM"`. L’élément de dimension `"AM"` s’applique à tous les accès de 12 :00 à 11 :59, tandis que l’élément de dimension `"PM"` s’applique à tous les accès de 12 :00 à 23 :59.
