---
title: Paniers
description: Le nombre d’accès pendant lesquels un visiteur a ajouté son premier produit au panier.
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
source-git-commit: e804907aa6655b4cfac146a34fb6a3774631818e
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 86%

---

# Paniers

La mesure &quot;Paniers&quot; indique le nombre d’accès pendant lesquels un visiteur a ajouté son premier produit à un panier.

## Méthode de calcul de cette mesure

Cette mesure tient compte du nombre d’accès dans lesquels `scOpen` se trouve dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).

## Différence entre les « Paniers » et les « Consultations du panier »

Puisque « Paniers » et « Consultations du panier » sont des événements qui nécessitent une mise en œuvre, votre entreprise détermine précisément la différence entre ces deux mesures. Cependant, Adobe a conçu ces mesures pour les cas suivants :

* La mesure « Paniers » ne se déclenche qu’une seule fois par achat lorsqu’un visiteur ajoute son premier produit au panier.
* La mesure « Ajouts au panier » se déclenche pour chaque produit ajouté au panier.

Pour le premier produit, les mesures « Paniers » et « Ajouts au panier » se déclenchent toutes les deux. Encore une fois, ces directives ne sont pas concrètes. Votre entreprise détermine la logique exacte de mise en œuvre.
