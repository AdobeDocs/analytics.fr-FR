---
title: Consultations de produit
description: Nombre de pages de produit vues.
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: eb13c3e828bc6d4c547f4529ee7a15182bbbf046
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 88%

---

# Consultations de produit

La mesure « Consultations de produit » indique le nombre de fois où un produit a été consulté. Cette mesure s’avère utile lorsque vous souhaitez afficher vos produits les plus consultés ou déterminer l’évolution des pages de produit vues au fil du temps.

## Méthode de calcul de cette mesure

Cette mesure comptabilise le nombre d’accès correspondant à **n’importe laquelle** des options suivantes :

* La valeur `prodView` existe dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md), ou
* Le [`products`](/help/implement/vars/page-vars/products.md) est définie, et la variable `events` est vide.
