---
title: Pages vues
description: Nombre de fois où un élément de dimension a été défini ou conservé dans Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: ht
source-wordcount: '169'
ht-degree: 100%

---

# Pages vues

La [mesure](overview.md) **[!UICONTROL Pages vues]** indique le nombre de fois où un élément de dimension donné a été défini ou conservé sur une page. Il s’agit de l’une des mesures de base les plus courantes dans les rapports.

## Méthode de calcul de cette mesure

Cette mesure comptabilise tous les appels de suivi de page vue ([`t()`](/help/implement/vars/functions/t-method.md)) d’une suite de rapports. Pour les dimensions, cela inclut les accès pour lesquels un élément de dimension est défini ou conservé. Cela n’inclut pas les appels de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)) ou les données des [Sources de données](/help/import/data-sources/overview.md).

## Comparaison avec des mesures similaires

* **Pages vues par rapport aux [visites](visits.md)** : les pages vues comptabilisent le nombre de fois où une page est consultée. Les visites comptabilisent le nombre de sessions des visiteurs et visiteuses. Une visite consiste en une ou plusieurs pages vues.
* **Pages vues par rapport aux [événements de page](page-events.md)** : les pages vues comptabilisent le nombre d’appels de suivi de pages vues (`t()`) et excluent les appels de suivi des liens (`tl()`). À l’inverse, les événements de page comptabilisent le nombre d’appels de suivi des liens et excluent les appels de suivi des pages vues.
