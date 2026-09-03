---
title: Moyenne de pages vues par visite
description: Nombre moyen de fois où un élément de dimension donné s’est affiché au cours d’une visite.
feature: Metrics
exl-id: fef6e803-e819-4f0f-8cb0-c565328a8bea
TQID: https://experienceleague.adobe.com/sospsPhk77O5qOLcMLmu7gB7rvlxbp8rGqB39LCnQ5g
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 216
ht-degree: 92%

---

# Moyenne de pages vues par visite

La dimension « Moyenne de pages vues par visite » indique le nombre moyen de pages vues en fonction de la dimension souhaitée. Pour les dimensions temporelles, vous pouvez suivre l’évolution du nombre moyen de pages vues au cours d’une visite et au fil du temps. Cette [mesure](overview.md) est utile lorsque vous souhaitez comprendre la fréquence d’affichage des éléments de dimension au cours d’une visite.

>[!TIP]
>
>Utilisez cette mesure avec une autre mesure ([Visites](visits.md), par exemple) pour obtenir de meilleurs informations. Si vous utilisez cette mesure seule, vous obtenez des éléments de dimension contenant des pages vues par visite anormales, qui sont généralement inutiles.

## Méthode de calcul de cette mesure

Cette mesure est calculée à l’aide de la formule [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Pourcentages supérieurs à 100 %

Cette mesure contient souvent des pourcentages supérieurs à 100 %. Le dénominateur correspond à la moyenne des pages vues par visite pour l’ensemble de la dimension, tandis que le numérateur correspond à la moyenne des pages vues par visite pour l’élément de dimension. Si la moyenne des pages vues par visite de l’ensemble de la dimension est inférieure à la moyenne des pages vues par visite d’un élément de dimension donné, les pourcentages sont supérieurs à 100 %. Le tri des rapports de classement selon cette mesure affiche une moyenne des pages vues par visite anormale, ce qui n’a généralement pas de valeur. Adobe recommande de trier selon une autre mesure, telle que [Visites](visits.md), dans les rapports de classement.
