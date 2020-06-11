---
title: Temps moyen passé sur le site
description: Durée moyenne pendant laquelle une valeur de dimension donnée existe entre les accès.
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 1%

---


# Temps moyen passé sur le site

La mesure Durée moyenne sur le site indique la durée écoulée entre les accès pour une valeur de dimension donnée. Cette mesure s’avère utile lorsque vous souhaitez afficher la durée moyenne passée pour des valeurs de dimension spécifiques. Vous pouvez également suivre la tendance de cette mesure au fil du temps pour voir comment change la durée globale de la visite. Cette mesure s’affiche au `HH:MM:SS` format.

Cette mesure est liée à la dimension [Durée de la visite](../dimensions/time-spent-per-visit.md) .

## Méthode de calcul de cette mesure

Pour une valeur de dimension donnée, prenez l’horodatage de chaque accès où cette valeur de dimension existe. Comparez-la à l’horodatage du prochain accès de la visite. Si l’accès n’a pas d’accès consécutif, ne l’incluez pas dans cette mesure. Sur l’ensemble du temps passé pour la valeur de dimension, divisez-les tous par le nombre de &quot;séquences&quot; pour cette valeur de dimension. Une &quot;séquence&quot; est l’endroit où la valeur d’une dimension est la même pour un ou plusieurs accès consécutifs. Ce nombre obtenu correspond à la mesure affichée dans les rapports.

Par exemple, considérez la visite suivante :

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


Si vous souhaitez obtenir une durée moyenne de consultation du site pour la valeur de la dimension `Product page A`, prenez tout d’abord la durée écoulée entre les accès pour cette dimension :

* **12:04:20 - 12:05:30** - 1 minute 10 secondes
* **12:05:30 - 12:07:00** - 1 minute 30 secondes
* **12:07:40 - 12:08:10** - 30 secondes
* **12:25:40 - ?** - Non inclus

La durée totale de la visite `Product page A` est `00:03:10`. Cette visite comportait deux séquences; la première séquence pour les deux valeurs consécutives et la seconde avant le passage en caisse. Le dernier accès de la visite n’est pas une séquence, puisqu’il n’existe pas d’horodatage de fin.

Le temps moyen passé sur le site `Product page A` est `00:01:35`.

## Temps moyen passé sur le site (secondes)

La mesure &quot;Durée moyenne de consultation du site (secondes)&quot; affiche les mêmes données présentées sous la forme d’un entier plutôt que sous `HH:MM:SS` forme de format. Cette mesure est la plus précieuse en tant que composant dans les mesures calculées.

## Les totaux de ventilation ne correspondent pas à l’élément de ligne parent.

La mesure Durée moyenne sur le site utilise des séquences ininterrompues d’une dimension donnée. La dimension de ventilation ne dépend pas de la dimension parente lors du calcul de ces séquences. Par exemple, considérez la visite suivante :

| `Timestamp` | `Page name` | `Site section` |
| --- | --- | --- |
| `12:00:00` | `Home` | `Foxes` |
| `12:00:30` | `Product` | `Foxes` |
| `12:02:10` | `Home` | `Foxes` |
| `12:02:20` | `(None; exit link click)` | `(None; exit link click)` |

Le calcul de la durée moyenne sur site pour la valeur de dimension `Home` utilise le calcul suivant :

```text
(30 + 10) / 2 = 20 seconds average time on site
```

Si vous appliquez une ventilation à l&#39;aide de la dimension Sections [du](../dimensions/site-section.md) site, le calcul suivant est utilisé :

```text
(30 + 10) / 1 = 40 seconds average time on site
```

Comme il n’y avait qu’une seule séquence dans la dimension de ventilation, elle utilise un dénominateur différent de sa dimension parent. Ces mesures fournissent généralement des résultats similaires au niveau d’une visite, mais peuvent être différents au niveau d’un accès.

## Pourcentages supérieurs à 100 %

Cette mesure contient fréquemment des pourcentages supérieurs à 100 %. Le dénominateur correspond à la durée moyenne de la dimension sur le site et le numérateur à la durée moyenne de la dimension sur le site. Si la durée moyenne sur site de la dimension entière est inférieure à la durée moyenne sur site d’une valeur de dimension donnée, vous verrez des pourcentages supérieurs à 100 %. Le tri des rapports avec classement selon cette mesure montre la durée moyenne d’anomalie sur les valeurs du site, ce qui n’a généralement pas de valeur. Adobe recommande le tri selon une autre mesure, telle que [Visites](visits.md), dans les rapports avec classement.

Voir Présentation [de la](time-spent.md) durée de la visite pour obtenir des informations plus générales sur la durée de la visite.
