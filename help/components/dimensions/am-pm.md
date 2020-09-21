---
title: Matin/après-midi
description: Détermine si l’accès s’est produit le matin ou l’après-midi.
translation-type: ht
source-git-commit: 322e2e87ab532d5e8a864dc06613a9b275c71df5
workflow-type: ht
source-wordcount: '117'
ht-degree: 100%

---


# Matin/après-midi

La dimension « Matin/Après-midi » permet de savoir si l’accès s’est produit le matin ou l’après-midi. L’heure de l’accès est basée sur le [fuseau horaire de la suite de rapports](/help/admin/admin/general-acct-settings-admin.md).

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi. Elle ne comporte aucun paramètre à modifier. Sa seule dépendance concerne le fuseau horaire de la suite de rapports, qui détermine les heures du matin et celles de l’après-midi.

## Éléments de dimension

Cette dimension contient toujours exactement deux éléments de dimension : `"AM"` et `"PM"`. L’élément de dimension `"AM"` s’applique à tous les accès de 00 h 00 à 11 h 59, tandis que l’élément de dimension `"PM"` s’applique à tous les accès de 12 h 00 à 23 h 59.
