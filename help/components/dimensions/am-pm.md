---
title: Matin/après-midi
description: Détermine si l’accès s’est produit le matin ou l’après-midi.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 64%

---

# Matin/après-midi

La [dimension](overview.md) « matin/après-midi » fournit insight si l’accès s’est produit aux heures du matin ou de l’après-midi. L’heure de l’accès est basée sur le [fuseau horaire de la suite de rapports](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi. Elle ne comporte aucun paramètre à modifier. Sa seule dépendance concerne le fuseau horaire de la suite de rapports, qui détermine les heures du matin et celles de l’après-midi.

## Éléments de dimension

Cette dimension contient toujours exactement deux éléments de dimension : `"AM"` et `"PM"`. L’élément de dimension `"AM"` s’applique à tous les accès de 12 :00 à 11 :59, tandis que l’élément de dimension `"PM"` s’applique à tous les accès de 12 :00 à 23 :59.
