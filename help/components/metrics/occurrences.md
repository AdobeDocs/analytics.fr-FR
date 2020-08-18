---
title: Occurrences
description: Nombre d’accès pour lesquels une variable a été définie ou conservée.
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 67%

---


# Occurrences

La mesure « Occurrences » indique le nombre d’accès pour lesquels une dimension donnée a été définie ou conservée. Lorsque vous faites glisser une dimension de Workspace vers un canevas vierge, Adobe applique automatiquement cette mesure au projet.

## Méthode de calcul de cette mesure

Sur tous les accès d’une suite de rapports, incluez les accès pour lesquels un élément de dimension est défini ou conservé. Certaines dimensions, telles que les [eVars](../dimensions/evar.md), persistent au-delà de l’accès pour lequel elles ont été définies. Cette mesure comptabilise à la fois les valeurs initiales et les valeurs conservées.

## Comparaison avec des mesures similaires

* **Occurrences vs[Instances](instances.md)**: Les occurrences comptabilisent les accès où un élément de dimension a été défini ou conservé. Les instances n’incluent pas les accès pour lesquels un élément de dimension persiste.
* **Occurrences par rapport aux[Pages vues](page-views.md)** : Occurrences inclut tous les types d’accès, y compris les appels de suivi de pages vues ([`t()`](/help/implement/vars/functions/t-method.md)) et les appels de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)). La mesure Pages vues inclut uniquement les appels de suivi de pages vues et exclut les appels de suivi des liens.
