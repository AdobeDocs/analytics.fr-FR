---
description: Nombre de captures d’une valeur spécifique, plus le nombre de pages vues pour lesquelles la valeur donnée était persistante. En d’autres termes, « Occurrences » fait référence à la somme des pages vues et des événements de page. Les occurrences sont disponibles dans Analysis Workspace et dans les Ad Hoc Analysis.
title: Occurrences
topic: Metrics
uuid: ff999fba-fcb7-4b16-9446-001facd0f15d
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Occurrences

Nombre de captures d’une valeur spécifique, plus le nombre de pages vues pour lesquelles la valeur donnée était persistante. En d’autres termes, « Occurrences » fait référence à la somme des pages vues et des événements de page. Les occurrences sont disponibles dans Analysis Workspace et dans les Ad Hoc Analysis.

## Comparaison des instances et des occurrences  {#section_4B0741AC1A78456E98AE0D4D28D70D29}

Deux mesures qui semblent similaires sont répertoriées :

**[Instances](/help/components/c-variables/c-metrics/metrics-instance.md)** : nombre de fois où une valeur a été définie pour une variable.

**Occurrences** : nombre de fois qu’une valeur a été définie ou conservée.

| Situation | Description |
|---|---|
| Occurrences supérieures aux instances | Il faut s’attendre à ce que cela se produise pour les variables de conversion, dans la mesure où les occurrences comprennent également le nombre de fois où la variable a été définie (instances). |
| Instances supérieures aux occurrences | Cela n’est pas possible dans le cadre des rapports, dans la mesure où toutes les instances sont également enregistrées en tant qu’occurrences. |
| Instances égales aux occurrences | Cette situation se présente généralement pour les variables de trafic, étant donné que, par définition, elles ne persistent pas au-delà de la demande d’image. |

>[!MORELIKETHIS]
>
>* [Instances](/help/components/c-variables/c-metrics/metrics-instance.md)

