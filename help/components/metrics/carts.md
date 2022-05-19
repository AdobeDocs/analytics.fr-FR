---
title: Paniers
description: Le nombre d’accès pendant lesquels un visiteur a ajouté son premier produit au panier.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
source-git-commit: 932a6c1452d4710b11c1ce5551c845ef6721f137
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 56%

---

# Paniers

La mesure Paniers indique le nombre d’accès pendant lesquels un visiteur a ajouté son premier produit au panier.

## Méthode de calcul de cette mesure

Cette mesure tient compte du nombre d’accès dans lesquels `scOpen` se trouve dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).

## Différence entre &quot;Paniers&quot;, &quot;Consultations du panier&quot; et &quot;Ajouts au panier&quot;

Puisque &quot;Paniers&quot;, &quot;Consultations du panier&quot; et &quot;Ajouts au panier&quot; sont des événements qui nécessitent une mise en oeuvre, votre entreprise détermine la différence précise entre ces mesures. Toutefois, Adobe a conçu ces mesures pour la logique suivante :

* La mesure « Paniers » ne se déclenche qu’une seule fois par achat lorsqu’un visiteur ajoute son premier produit au panier.
* &quot;Consultations du panier&quot; se déclenche chaque fois qu’un visiteur consulte son panier.
* La mesure « Ajouts au panier » se déclenche pour chaque produit ajouté au panier.

Lorsqu’un client ajoute son premier produit à un panier, le comportement prévu est que les paniers et les ajouts au panier se déclenchent. Encore une fois, ces directives ne sont pas concrètes. Votre entreprise détermine la logique exacte de mise en œuvre.
