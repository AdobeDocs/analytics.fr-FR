---
title: Paniers
description: Le nombre d’accès pendant lesquels un visiteur a ajouté son premier produit au panier.
translation-type: ht
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: ht
source-wordcount: '157'
ht-degree: 100%

---


# Paniers

La mesure « Retraits du panier » indique le nombre de fois qu’un visiteur a supprimé un article du panier. Cette mesure s’avère utile lorsque vous souhaitez comprendre la partie de l’entonnoir de conversion dans laquelle les clients ne s’intéressent plus à un produit.

## Méthode de calcul de cette mesure

Cette mesure tient compte du nombre d’accès dans lesquels `scOpen` se trouve dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).

## Différence entre les « Paniers » et les « Consultations du panier »

Puisque « Paniers » et « Consultations du panier » sont des événements qui nécessitent une mise en œuvre, votre entreprise détermine précisément la différence entre ces deux mesures. Cependant, Adobe a conçu ces mesures pour les cas suivants :

* La mesure « Paniers » ne se déclenche qu’une seule fois par achat lorsqu’un visiteur ajoute son premier produit au panier.
* La mesure « Ajouts au panier » se déclenche pour chaque produit ajouté au panier.

Pour le premier produit, les mesures « Paniers » et « Ajouts au panier » se déclenchent toutes les deux. Encore une fois, ces directives ne sont pas concrètes. Votre entreprise détermine la logique exacte de mise en œuvre.
