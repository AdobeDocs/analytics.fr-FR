---
title: 'Mesure Pages vues expliquée | Adobe Analytics '
description: Découvrez comment la mesure relative aux vues de page est traitée dans Adobe Analytics et saisissez également la différence entre les vues de page et les visites.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 100%

---

# En savoir plus sur les Vues de page avec Adobe Analytics

La mesure « Pages vues » indique le nombre de fois où un élément de dimension donné a été défini ou conservé sur une page. Il s’agit de l’une des mesures de base les plus courantes dans les rapports.

## Méthode de calcul de cette mesure

Cette mesure comptabilise tous les appels de suivi de page vue ([`t()`](/help/implement/vars/functions/t-method.md)) d’une suite de rapports. Pour les dimensions, elle inclut les accès pour lesquels un élément de dimension est défini ou conservé. Elle n’inclut pas les appels de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Comparaison avec des mesures similaires

* **Pages vues par rapport aux [visites](visits.md)** : les pages vues comptabilisent le nombre de fois où une page est consultée. Les visites comptabilisent le nombre de sessions des visiteurs. Une visite consiste en une ou plusieurs pages.
* **Pages vues par rapport aux [événements de page](page-events.md)** : les pages vues comptabilisent le nombre d’appels de suivi de page vue (`t()`) et excluent les appels de suivi des liens (`tl()`). Les événements de page ont un fonctionnement contraire : ils comptabilisent le nombre d’appels de suivi des liens et excluent les pages vues.
