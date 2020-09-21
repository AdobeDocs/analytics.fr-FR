---
title: Occurrences
description: Nombre d’accès pour lesquels une variable a été définie ou conservée.
translation-type: ht
source-git-commit: 322e2e87ab532d5e8a864dc06613a9b275c71df5
workflow-type: ht
source-wordcount: '153'
ht-degree: 100%

---


# Occurrences

La mesure « Occurrences » indique le nombre d’accès pour lesquels une dimension donnée a été définie ou conservée. Lorsque vous faites glisser une dimension de Workspace vers un canevas vierge, Adobe applique automatiquement cette mesure au projet.

## Méthode de calcul de cette mesure

Sur tous les accès d’une suite de rapports, incluez les accès pour lesquels un élément de dimension est défini ou conservé. Certaines dimensions, telles que les [eVars](../dimensions/evar.md), persistent au-delà de l’accès pour lequel elles ont été définies. Cette mesure comptabilise à la fois les valeurs initiales et les valeurs conservées.

## Comparaison avec des mesures similaires

* **Occurrences par rapport aux[Instances](instances.md)** : Occurrences comptabilise les accès où un élément de dimension a été défini ou conservé. Les instances n’incluent pas les accès pour lesquels un élément de dimension persiste.
* **Occurrences par rapport aux[Pages vues](page-views.md)** : Occurrences inclut tous les types d’accès, y compris les appels de suivi de pages vues ([`t()`](/help/implement/vars/functions/t-method.md)) et les appels de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)). La mesure Pages vues inclut uniquement les appels de suivi de pages vues et exclut les appels de suivi des liens.
