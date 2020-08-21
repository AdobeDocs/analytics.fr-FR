---
title: Matin/après-midi
description: Détermine si l’accès s’est produit le matin ou l’après-midi.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 70%

---


# Matin/après-midi

La dimension « Matin/Après-midi » permet de savoir si l’accès s’est produit le matin ou l’après-midi. L’heure de l’accès est basée sur le [fuseau horaire de la suite de rapports](/help/admin/admin/general-acct-settings-admin.md).

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi. Elle ne comporte aucun paramètre à modifier. Sa seule dépendance concerne le fuseau horaire de la suite de rapports, qui détermine les heures du matin et celles de l’après-midi.

## Éléments de Dimension

This dimension always contains exactly two dimension items: `"AM"` and `"PM"`. The dimension item `"AM"` applies to all hits from 12:00 AM to 11:59 AM, while the dimension item `"PM"` applies to all hits from 12:00 PM to 11:59 PM.
