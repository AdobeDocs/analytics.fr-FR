---
title: Occurrences
description: Nombre d’accès pour lesquels une variable a été définie ou conservée.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 1%

---


# Occurrences

La mesure &quot;Occurrences&quot; indique le nombre d’accès pour lesquels une dimension donnée a été définie ou conservée. Lorsque vous faites glisser une dimension de Workspace vers un canevas vierge, Adobe applique automatiquement cette mesure au projet.

## Méthode de calcul de cette mesure

Sur tous les accès d’une suite de rapports, incluez les accès pour lesquels une valeur de dimension est définie ou conservée. Certaines dimensions, telles que les [eVars](../dimensions/evar.md), persistent au-delà de l’accès défini. Les mesures telles que vues [de](page-views.md) page et [Occurrences](occurrences.md) comptabilisent à la fois les valeurs initiales et les valeurs persistantes. Cette mesure ne comptabilise pas les valeurs conservées.

## Comparaison avec des mesures similaires

* **Occurrences vs[Instances](instances.md)**: Nombre d’occurrences où une valeur de dimension a été définie ou conservée. Les instances n’incluent pas les accès pour lesquels une valeur de dimension persiste.
* **Occurrences par rapport aux vues[de](page-views.md)**page : Les occurrences comprennent tous les types d’accès, y compris les appels de suivi de vue de page ([`t()`](/help/implement/vars/functions/t-method.md)) et les appels de suivi de liens ([`tl()`](/help/implement/vars/functions/tl-method.md)). La mesure vues de page inclut uniquement les appels de suivi de vue de page et exclut les appels de suivi de lien.