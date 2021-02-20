---
title: Pages vues
description: Nombre de fois où une page a été consultée.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 100%

---


# Pages vues

La mesure « Pages vues » indique le nombre de fois où un élément de dimension donné a été défini ou conservé sur une page. Il s’agit de l’une des mesures de base les plus courantes dans les rapports.

## Méthode de calcul de cette mesure

Cette mesure comptabilise tous les appels de suivi de page vue ([`t()`](/help/implement/vars/functions/t-method.md)) d’une suite de rapports. Pour les dimensions, elle inclut les accès pour lesquels un élément de dimension est défini ou conservé. Elle n’inclut pas les appels de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Comparaison avec des mesures similaires

* **Pages vues par rapport aux [visites](visits.md)** : les pages vues comptabilisent le nombre de fois où une page est consultée. Les visites comptabilisent le nombre de sessions des visiteurs. Une visite consiste en une ou plusieurs pages.
* **Pages vues par rapport aux [événements de page](page-events.md)** : les pages vues comptabilisent le nombre d’appels de suivi de page vue (`t()`) et excluent les appels de suivi des liens (`tl()`). Les événements de page ont un fonctionnement contraire : ils comptabilisent le nombre d’appels de suivi des liens et excluent les pages vues.