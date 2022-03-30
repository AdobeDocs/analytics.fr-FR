---
title: Pages vues
description: Nombre de fois où un élément de dimension a été défini ou conservé dans Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 65f87bf4b5b3897c9ef68d091858332c08cbf699
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 39%

---

# Pages vues

La mesure « Pages vues » indique le nombre de fois où un élément de dimension donné a été défini ou conservé sur une page. Il s’agit de l’une des mesures de base les plus courantes dans les rapports.

## Méthode de calcul de cette mesure

Cette mesure comptabilise tous les appels de suivi de page vue ([`t()`](/help/implement/vars/functions/t-method.md)) d’une suite de rapports. Pour les dimensions, elle inclut les accès pour lesquels un élément de dimension est défini ou conservé. Elle n’inclut pas les appels de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Comparaison avec des mesures similaires

* **Pages vues par rapport à [Visites](visits.md)**: Les pages vues comptabilisent le nombre de fois où une page est consultée. Les visites comptabilisent le nombre de sessions des visiteurs. Une visite consiste en une ou plusieurs pages vues.
* **Pages vues par rapport à [Événements de page](page-events.md)**: Les pages vues comptabilisent le nombre d’appels de suivi de pages vues (`t()`) et exclut les appels de suivi des liens (`tl()`). Les événements de page sont l’inverse. ils comptabilisent le nombre d’appels de suivi de liens et excluent les appels de suivi de pages vues.
