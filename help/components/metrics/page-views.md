---
title: 'Mesure Vues de page expliquée | Adobe Analytics '
description: Découvrez comment la mesure vues de page est traitée dans Adobe Analytics et comprenez également la différence entre les vues de page et les visites.
translation-type: tm+mt
source-git-commit: c588087b949093152435967f62e43758e9e86208
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 80%

---


# En savoir plus sur les Vues de pages avec Adobe Analytics

La mesure « Pages vues » indique le nombre de fois où un élément de dimension donné a été défini ou conservé sur une page. Il s’agit de l’une des mesures de base les plus courantes dans les rapports.

## Méthode de calcul de cette mesure

Cette mesure comptabilise tous les appels de suivi de page vue ([`t()`](/help/implement/vars/functions/t-method.md)) d’une suite de rapports. Pour les dimensions, elle inclut les accès pour lesquels un élément de dimension est défini ou conservé. Elle n’inclut pas les appels de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Comparaison avec des mesures similaires

* **Pages vues par rapport aux [visites](visits.md)** : les pages vues comptabilisent le nombre de fois où une page est consultée. Les visites comptabilisent le nombre de sessions des visiteurs. Une visite consiste en une ou plusieurs pages.
* **Pages vues par rapport aux [événements de page](page-events.md)** : les pages vues comptabilisent le nombre d’appels de suivi de page vue (`t()`) et excluent les appels de suivi des liens (`tl()`). Les événements de page ont un fonctionnement contraire : ils comptabilisent le nombre d’appels de suivi des liens et excluent les pages vues.