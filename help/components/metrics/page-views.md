---
title: Pages vues
description: Nombre de fois où un élément de dimension a été défini ou conservé dans Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 60a630c9934d613aa69523bdb87b92165a135eb9
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 18%

---

# Pages vues

Le **[!UICONTROL Pages vues]** mesure indique le nombre de fois où un élément de dimension donné (valeur de dimension) a été défini ou conservé (c’est-à-dire lorsqu’il expire) sur une page. Il s’agit de l’une des mesures de base les plus courantes dans les rapports.

Par exemple, la variable [!UICONTROL Jours de la semaine] est composée des éléments de dimension suivants : Dimanche, lundi, mardi, mercredi, jeudi, vendredi et samedi.

## Méthode de calcul de cette mesure

Cette mesure comptabilise tous les appels de suivi de page vue ([`t()`](/help/implement/vars/functions/t-method.md)) d’une suite de rapports. Pour les dimensions, elle inclut les accès pour lesquels un élément de dimension est défini ou conservé. Elle n’inclut pas les appels de suivi de liens ([`tl()`](/help/implement/vars/functions/tl-method.md)) ou des données du résumé [Sources de données](/help/import/data-sources/overview.md).

## Comparaison avec des mesures similaires

* **Pages vues par rapport à [Visites](visits.md)**: Les pages vues comptabilisent le nombre de fois où une page est consultée. Les visites comptabilisent le nombre de sessions des visiteurs. Une visite peut être composée d’une ou de plusieurs pages vues.
* **Pages vues par rapport à [Événements de page](page-events.md)**: Les pages vues comptabilisent le nombre d’appels de suivi de pages vues (`t()`) et exclut les appels de suivi des liens (`tl()`). Les événements de page sont l’inverse. ils comptabilisent le nombre d’appels de suivi de liens et excluent les appels de suivi de pages vues.
