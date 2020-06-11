---
title: Paniers
description: Nombre de visites où un visiteur a ajouté son premier produit à un panier.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# Paniers

La mesure &quot;Suppressions de panier&quot; indique le nombre de fois où un visiteur a supprimé un élément de son panier. Cette mesure s’avère utile lorsque vous souhaitez comprendre la partie de l’entonnoir de conversion dans laquelle les clients ne s’intéressent plus à un produit.

## Méthode de calcul de cette mesure

Cette mesure compte le nombre d’accès où `scOpen` se trouve la [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable.

## Différence entre les &quot;paniers&quot; et les &quot;vues au panier&quot;

Puisque les paniers et les vues de panier sont des événements qui nécessitent une mise en oeuvre, votre entreprise décide de la différence précise entre ces deux mesures. Cependant, Adobe a conçu ces mesures pour les éléments suivants :

* Les paniers ne se déclenchent qu’une seule fois par achat lorsqu’un visiteur ajoute son premier produit à son panier.
* Les &quot;ajouts au panier&quot; déclenchent pour chaque produit ajouté à leur panier.

Pour le premier produit, les déclencheurs &quot;Paniers&quot; et &quot;Ajouts au panier&quot; se déclenchent. Là encore, ces lignes directrices ne sont pas concrètes; votre organisation détermine la logique d’implémentation exacte.
