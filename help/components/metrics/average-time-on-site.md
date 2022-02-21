---
title: Durée moyenne de la visite du site
description: La durée moyenne d’existence d’un élément de dimension donné entre les accès.
feature: Metrics
exl-id: bf9056e2-4f6d-4c4f-b641-d3146ce269ff
source-git-commit: 7966c7d9add0011831c97fbe0dfcca2acd8afb58
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 99%

---

# Durée moyenne de la visite du site

La mesure « Durée moyenne de la visite du site » indique le temps écoulé entre les accès pour un élément de dimension donné. Cette mesure s’avère utile lorsque vous souhaitez afficher la durée moyenne d’éléments de dimension spécifiques. Vous pouvez également suivre la tendance de cette mesure au fil du temps pour observer l’évolution de la durée globale. Cette mesure s’affiche au format `HH:MM:SS`.

Cette mesure est liée à la dimension [Durée de la visite](../dimensions/time-spent-per-visit.md).

## Méthode de calcul de cette mesure

Pour un élément de dimension donné, prenez la date et l’heure de chaque accès où cet élément de dimension existe. Comparez-les avec la date et l’heure du prochain accès de la visite. Si l’accès n’est pas suivi d’un accès consécutif, ne l’incluez pas dans cette mesure. Divisez l’ensemble du temps passé pour l’élément de dimension par le nombre de « séquences » de celui-ci. Une « séquence » correspond à un élément de dimension identique pour un ou plusieurs accès consécutifs. Ce nombre obtenu correspond à la mesure affichée dans les rapports.

Prenons pour exemple la visite suivante :

| `Timestamp` | `Page` |
| --- | --- |
| `12:03:00` | `Home page` |
| `12:04:20` | `Product page A` |
| `12:05:30` | `Product page A` |
| `12:07:00` | `Product page B` |
| `12:07:40` | `Product page A` |
| `12:08:10` | `Checkout` |
| `12:10:00` | `Purchase` |
| `12:25:00` | `Home page` |
| `12:25:40` | `Product page A` |


Si vous souhaitez obtenir la durée moyenne de la visite du site pour l’élément de la dimension `Product page A`, prenez tout d’abord le temps écoulé entre les accès pour cette dimension :

* **12:04:20 à 12:05:30** - 1 minute 10 secondes
* **12:05:30 à 12:07:00** - 1 minute 30 secondes
* **12:07:40 à 12:08:10** - 30 secondes
* **12:25:40 - ?** - Non inclus

La durée totale de la visite pour `Product page A` correspond à `00:03:10`. Cette visite comportait deux séquences ; la première séquence pour les deux valeurs consécutives et la seconde avant le passage en caisse. Le dernier accès de la visite n’est pas une séquence, puisqu’il n’existe pas de date et heure de fin.

La durée moyenne de la visite du site pour `Product page A` correspond à `00:01:35`.

>[!NOTE]
>
>Cette mesure affiche la valeur `"Invalid"` si l’élément de dimension contient uniquement les accès qui se trouvaient en dernier au cours d’une visite. Cette mesure nécessite un accès ultérieur pour effectuer le suivi de la durée de la visite.

## Temps moyen passé sur le site (secondes)

La mesure « Durée moyenne de la visite du site (en secondes) » affiche les mêmes données présentées sous la forme d’un entier plutôt qu’au format `HH:MM:SS`. Cette mesure est particulièrement utile en tant que composant des mesures calculées.

## Les totaux de ventilation ne correspondent pas à l’élément de ligne parent

La mesure « Durée moyenne de la visite du site » utilise des séquences ininterrompues d’une dimension donnée. La dimension de ventilation ne dépend pas de la dimension parent lors du calcul de ces séquences. Prenons pour exemple la visite suivante :

| `Timestamp` | `Page name` | `Site section` |
| --- | --- | --- |
| `12:00:00` | `Home` | `Foxes` |
| `12:00:30` | `Product` | `Foxes` |
| `12:02:10` | `Home` | `Foxes` |
| `12:02:20` | `(None; exit link click)` | `(None; exit link click)` |

Le calcul de la durée moyenne de la visite du site pour l’élément de dimension `Home` utilise le calcul suivant :

```text
(30 + 10) / 2 = 20 seconds average time on site
```

Si vous appliquez une ventilation à l’aide de la dimension [Sections du site](../dimensions/site-section.md), le calcul suivant est utilisé :

```text
(30 + 10) / 1 = 40 seconds average time on site
```

Comme la dimension de ventilation ne comportait qu’une seule séquence, elle utilise un dénominateur différent de celui de sa dimension parent. Ces mesures donnent généralement des résultats similaires au niveau de la visite, mais elles peuvent être différentes au niveau de l’accès.

## Pourcentages supérieurs à 100 %

Cette mesure contient souvent des pourcentages supérieurs à 100 %. Le dénominateur correspond à la durée moyenne de la visite du site de l’ensemble de la dimension et le numérateur à celle de l’élément de dimension. Si la durée moyenne de la visite du site de l’ensemble de la dimension est inférieure à celle de l’élément de dimension donné, vous verrez des pourcentages supérieurs à 100 %. Le tri des rapports de classement en fonction de cette mesure affiche les valeurs d’anomalie du temps moyen passé sur le site, qui sont généralement inutiles. Adobe recommande de trier selon une autre mesure, telle que [Visites](visits.md), dans les rapports de classement.

Consultez [Présentation de la durée de consultation](time-spent.md) pour obtenir des informations plus générales sur la durée de consultation.
