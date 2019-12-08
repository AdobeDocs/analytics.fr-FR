---
description: Une couche de données est une structure d’objets JavaScript que les développeurs insèrent sur les pages.
keywords: Analytics Implementation;data layer;digitalData
title: Couche de données
topic: Developer and implementation
uuid: dedb2a50-06f3-4354-8993-a25d4952ce1e
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Couche de données

Une _couche de données_ est une structure d’objets JavaScript que les développeurs insèrent sur les pages. Elle peut être utilisée par les outils de suivi (y compris les systèmes de gestion des balises comme Adobe Experience Platform Launch et Dynamic Tag Management) afin de remplir des rapports.

La mise en œuvre d’une couche de données sur votre site procure la plus grande flexibilité et le meilleur contrôle sur votre mise en œuvre et facilite la maintenance dans les phases ultérieures. Les noms de ces objets JavaScript sont en théorie arbitraires, mais une bonne pratique est d’utiliser des noms cohérents et prévisibles. Il est possible que les développeurs disposent déjà d’une couche de données ou qu’ils préfèrent un certain format. La communauté de suivi a créé différents standards comme point de départ. Le document de spécification [Mise en œuvre de la couche de données pour Analytics](assets/datalayer-documentation.pdf) utilise l’objet digitalData standard du W3C accepté par le plus grand nombre de technologies de suivi, dans le cas où la couche de données est utilisée à d’autres fins que cette mise en œuvre de gestion dynamique des balises.
