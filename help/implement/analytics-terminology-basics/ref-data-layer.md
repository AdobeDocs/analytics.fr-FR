---
description: Une couche de données est une structure d’objets JavaScript que les développeurs insèrent sur les pages.
keywords: Implémentation d'Analytics ; couche de données ; Digitaldata
seo-description: Une couche de données est une structure d’objets JavaScript que les développeurs insèrent sur les pages. Elle peut être utilisée par les outils de suivi (y compris les systèmes de Tag Management comme Dynamic Tag Management) afin de remplir des rapports.
seo-title: Couche de données
solution: Analytics
title: Couche de données
topic: Développeur et mise en œuvre
uuid: dedb 2 a 50-06 f 3-4354-8993-a 25 d 4952 ce 1 e
translation-type: tm+mt
source-git-commit: 26c3cc9895c27d6abc452e0a4636771fb2415fb3

---


# Couche de données

A _data layer_ is a framework of JavaScript objects that developers insert into pages. Les couches de données peuvent être utilisées par les outils de suivi (notamment les systèmes de gestion des balises tels qu'Adobe Experience Platform Launch et la gestion dynamique des balises) pour renseigner les rapports.

La mise en œuvre d’une couche de données sur votre site procure la plus grande flexibilité et le meilleur contrôle sur votre mise en œuvre et facilite la maintenance dans les phases ultérieures. Les noms de ces objets JavaScript sont en théorie arbitraires, mais une bonne pratique est d’utiliser des noms cohérents et prévisibles. Les développeurs peuvent déjà disposer d'une couche de données ou d'une préférence pour le format. La communauté de suivi a créé différents standards comme point de départ. Le document de spécification [Mise en œuvre de la couche de données pour Analytics](assets/datalayer-documentation.pdf) utilise l’objet digitalData standard du W3C accepté par le plus grand nombre de technologies de suivi, dans le cas où la couche de données est utilisée à d’autres fins que cette mise en œuvre de gestion dynamique des balises.
