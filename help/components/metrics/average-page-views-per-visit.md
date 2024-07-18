---
title: Moyenne de pages vues par visite
description: Nombre moyen de fois où un élément de dimension donné s’est affiché au cours d’une visite.
feature: Metrics
exl-id: fef6e803-e819-4f0f-8cb0-c565328a8bea
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 92%

---

# Moyenne de pages vues par visite

La dimension « Moyenne de pages vues par visite » indique le nombre moyen de pages vues en fonction de la dimension souhaitée. Pour les dimensions temporelles, vous pouvez suivre l’évolution du nombre moyen de pages vues au cours d’une visite et au fil du temps. Cette [mesure](overview.md) s’avère utile pour comprendre la fréquence d’affichage des éléments de dimension lors d’une visite.

>[!TIP]
>
>Utilisez cette mesure avec une autre mesure ([Visites](visits.md), par exemple) pour obtenir de meilleurs informations. Si vous utilisez cette mesure seule, vous obtenez des éléments de dimension contenant des pages vues par visite anormales, qui sont généralement inutiles.

## Méthode de calcul de cette mesure

Cette mesure est calculée à l’aide de la formule [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Pourcentages supérieurs à 100 %

Cette mesure contient souvent des pourcentages supérieurs à 100 %. Le dénominateur correspond à la moyenne des pages vues par visite pour l’ensemble de la dimension, tandis que le numérateur correspond à la moyenne des pages vues par visite pour l’élément de dimension. Si la moyenne des pages vues par visite de l’ensemble de la dimension est inférieure à la moyenne des pages vues par visite d’un élément de dimension donné, les pourcentages sont supérieurs à 100 %. Le tri des rapports de classement selon cette mesure affiche une moyenne des pages vues par visite anormale, ce qui n’a généralement pas de valeur. Adobe recommande de trier selon une autre mesure, telle que [Visites](visits.md), dans les rapports de classement.
