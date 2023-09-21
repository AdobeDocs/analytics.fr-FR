---
title: Consultations de produit
description: Nombre de pages de produit vues.
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 72%

---

# Consultations de produit

&quot;Consultations produits&quot; [metric](overview.md) indique le nombre de fois où un produit a été consulté. Cette mesure s’avère utile lorsque vous souhaitez afficher vos produits les plus consultés ou déterminer l’évolution des pages de produit vues au fil du temps.

## Méthode de calcul de cette mesure

Cette mesure comptabilise le nombre d’accès correspondant à **n’importe laquelle** des options suivantes :

* La valeur `prodView` existe dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md), ou
* La variable [`products`](/help/implement/vars/page-vars/products.md) est définie, et la variable `events` est vide.
