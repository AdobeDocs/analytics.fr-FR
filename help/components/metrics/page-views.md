---
title: Pages vues
description: Nombre de fois où une page a été consultée.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 2%

---


# Pages vues

La mesure &quot;vues de page&quot; indique le nombre de fois où un élément de dimension donné a été défini ou conservé sur une page. Il s’agit de l’une des mesures de base les plus courantes dans les rapports.

## Méthode de calcul de cette mesure

Cette mesure comptabilise tous les appels de suivi de vue de page ([`t()`](/help/implement/vars/functions/t-method.md)) d’une suite de rapports. Pour les dimensions, il inclut les accès où un élément de dimension est défini ou conservé. Il n’inclut pas les appels de suivi de liens ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Comparaison avec des mesures similaires

* **vues de page par rapport aux[visites](visits.md)**: Les vues de page comptabilisent le nombre de fois où une page est consultée. Les visites comptabilisent le nombre de sessions pour les visiteurs. Une visite consiste en une ou plusieurs pages.
* **vues de page par rapport aux événements[de](page-events.md)**page : Les vues de page comptabilisent le nombre d’appels de suivi de vue de page (`t()`) et excluent les appels de suivi de lien (`tl()`). Les événements de page sont le contraire ; il comptabilise le nombre d’appels de suivi des liens et exclut les vues de page.