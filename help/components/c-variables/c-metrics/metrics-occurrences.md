---
description: Nombre de captures d’une valeur spécifique, plus le nombre de pages vues pour lesquelles la valeur donnée était persistante. En d’autres termes, « Occurrences » fait référence à la somme des pages vues et des événements de page. Les occurrences sont disponibles dans Analysis Workspace et dans les Ad Hoc Analysis.
seo-description: Nombre de captures d’une valeur spécifique, plus le nombre de pages vues pour lesquelles la valeur donnée était persistante. En d’autres termes, « Occurrences » fait référence à la somme des pages vues et des événements de page. Les occurrences sont disponibles dans Analysis Workspace et dans les Ad Hoc Analysis.
seo-title: Occurrences
solution: Analytics
title: Occurrences
topic: Mesures
uuid: ff 999 fba-fcb 7-4 b 16-9446-001 facd 0 f 15 d
translation-type: tm+mt
source-git-commit: ecc762f73f9a303cebf48668b807fef9a2f055c5

---


# Occurrences

Nombre de captures d’une valeur spécifique, plus le nombre de pages vues pour lesquelles la valeur donnée était persistante. En d’autres termes, « Occurrences » fait référence à la somme des pages vues et des événements de page. Les occurrences sont disponibles dans Analysis Workspace et dans les Ad Hoc Analysis.

## Comparaison des instances et des occurrences {#section_4B0741AC1A78456E98AE0D4D28D70D29}

Deux mesures qui semblent similaires sont répertoriées :

**[Instances](../../../components/c-variables/c-metrics/metrics-instance.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF)** : nombre de fois où une valeur a été définie pour une variable.

**Occurrences** : nombre de fois qu’une valeur a été définie ou conservée.

| Situation | Description |
|---|---|
| Occurrences supérieures aux instances | Il faut s’attendre à ce que cela se produise pour les variables de conversion, dans la mesure où les occurrences comprennent également le nombre de fois où la variable a été définie (instances). |
| Instances supérieures aux occurrences | Cela n’est pas possible dans le cadre des rapports, dans la mesure où toutes les instances sont également enregistrées en tant qu’occurrences. |
| Instances égales aux occurrences | Cette situation se présente généralement pour les variables de trafic, étant donné que, par définition, elles ne persistent pas au-delà de la demande d’image. |

>[!MORE_LIKE_THIS]
>
>* [Instances](/help/components/c-variables/c-metrics/metrics-instance.md)

