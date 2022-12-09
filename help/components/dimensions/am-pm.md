---
title: Matin/après-midi
description: Détermine si l’accès s’est produit le matin ou l’après-midi.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
source-git-commit: 35e7c8bccb8524fa5e87cae223f0854956c7528a
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 100%

---

# Matin/après-midi

La dimension « Matin/Après-midi » permet de savoir si l’accès s’est produit le matin ou l’après-midi. L’heure de l’accès est basée sur le [fuseau horaire de la suite de rapports](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md).

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi. Elle ne comporte aucun paramètre à modifier. Sa seule dépendance concerne le fuseau horaire de la suite de rapports, qui détermine les heures du matin et celles de l’après-midi.

## Éléments de dimension

Cette dimension contient toujours exactement deux éléments de dimension : `"AM"` et `"PM"`. L’élément de dimension `"AM"` s’applique à tous les accès de 00 h 00 à 11 h 59, tandis que l’élément de dimension `"PM"` s’applique à tous les accès de 12 h 00 à 23 h 59.
