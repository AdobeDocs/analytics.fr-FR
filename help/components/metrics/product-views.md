---
title: vues de produits
description: Nombre de vues aux pages de produits.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 0%

---


# vues de produits

La mesure &quot;vues de produits&quot; indique le nombre de fois où un produit a été consulté. Cette mesure s’avère utile lorsque vous souhaitez afficher vos produits les plus consultés ou déterminer l’évolution des vues totales de produits au fil du temps.

## Méthode de calcul de cette mesure

Cette mesure comptabilise le nombre d’accès qui correspondent à **l’une** des mesures suivantes :

* La valeur `prodView` existe dans la [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable ; ou
* La [`products`](/help/implement/vars/page-vars/products.md) variable est définie et aucun événement de panier n’existe dans la `events` variable. Tout événement non personnalisé (`event1` - `event1000`) est un événement de panier.