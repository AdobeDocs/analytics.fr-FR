---
title: Matin/après-midi
description: Détermine si l’accès s’est produit pendant les heures AM ou PM.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 3%

---


# Matin/après-midi

La dimension &quot;AM/PM&quot; permet de savoir si l’accès s’est produit pendant les heures AM ou PM. The time of the hit is based on the [report suite&#39;s time zone](/help/admin/admin/general-acct-settings-admin.md).

## Renseigner cette dimension avec des données

Cette dimension est prête à l&#39;emploi. Il n&#39;a aucun paramètre à modifier. Sa seule dépendance concerne le fuseau horaire de la suite de rapports, qui détermine les heures AM et PM.

## Éléments de dimension

Cette dimension contient toujours exactement deux éléments de dimension : `"AM"` et `"PM"`. L’élément de dimension `"AM"` s’applique à tous les accès de 12h00 à 11h59, tandis que l’élément de dimension `"PM"` s’applique à tous les accès de 12h00 à 23h59.
