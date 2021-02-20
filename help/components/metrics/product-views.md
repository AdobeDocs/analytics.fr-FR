---
title: Consultations de produit
description: Nombre de pages de produit vues.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 100%

---


# Consultations de produit

La mesure « Consultations de produit » indique le nombre de fois où un produit a été consulté. Cette mesure s’avère utile lorsque vous souhaitez afficher vos produits les plus consultés ou déterminer l’évolution des pages de produit vues au fil du temps.

## Méthode de calcul de cette mesure

Cette mesure comptabilise le nombre d’accès correspondant à **n’importe laquelle** des options suivantes :

* La valeur `prodView` existe dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md), ou
* La variable [`products`](/help/implement/vars/page-vars/products.md) est définie et aucun événement de panier n’existe dans la variable `events`. Tout événement non personnalisé (`event1` - `event1000`) est un événement de panier.