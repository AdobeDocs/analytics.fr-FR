---
title: Paniers
description: Le nombre d’accès pendant lesquels un visiteur a ajouté son premier produit au panier.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 45%

---

# Paniers

La mesure Paniers [mesure](overview.md) indique le nombre d’accès pendant lesquels un visiteur a ajouté son premier produit au panier.

## Méthode de calcul de cette mesure

Cette mesure tient compte du nombre d’accès dans lesquels `scOpen` se trouve dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).

## Différence entre « Paniers », « Vues du panier » et « Ajouts au panier »

Étant donné que les « paniers », « consultations du panier » et « ajouts au panier » sont des événements qui nécessitent une implémentation, votre entreprise décide de la différence précise entre ces mesures. Cependant, Adobe a conçu ces mesures pour la logique suivante :

* La mesure « Paniers » ne se déclenche qu’une seule fois par achat lorsqu’un visiteur ajoute son premier produit au panier.
* Les « consultations du panier » se déclenchent chaque fois qu’un visiteur consulte son panier.
* La mesure « Ajouts au panier » se déclenche pour chaque produit ajouté au panier.

Lorsqu’un client ajoute son premier produit à un panier, le comportement prévu est que les options « Paniers » et « Ajouts au panier » se déclenchent. Encore une fois, ces directives ne sont pas concrètes. Votre entreprise détermine la logique exacte de mise en œuvre.
