---
title: Fidélité de la clientèle
description: Catégories basées sur le nombre d’achats précédents effectués par un visiteur.
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---


# Fidélité de la clientèle

La dimension &quot;Fidélité de la clientèle&quot; indique le nombre de visiteurs de votre site qui ont effectué 0 achat préalable, 1 achat préalable, 2 achats antérieurs ou 3 achats antérieurs ou plus. Cette dimension est utile pour comprendre comment votre site affecte le comportement d’achat. Vous pouvez également utiliser cette dimension dans un segment pour vous concentrer sur les visiteurs qui reviennent faire un achat, afin d’encourager un comportement similaire pour les nouveaux visiteurs.

## Renseigner cette dimension avec des données

Adobe remplit automatiquement cette dimension en fonction du [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) événement de votre mise en oeuvre. Si vous implémentez le `purchase` événement sur votre site, cette dimension fonctionne toujours.

## Valeurs de dimension

Les valeurs de dimension sont les suivantes :

* **Pas un client**: Au moment de l’accès, le visiteur n’a jamais effectué d’achat auparavant.
* **Nouveaux clients**: Au moment de l’accès, le visiteur a effectué un seul achat auparavant.
* **Clients** de retour : Au moment de l’accès, le visiteur a effectué deux achats auparavant.
* **Clients** fidèles : Au moment de l’accès, le visiteur a effectué trois achats ou plus auparavant.

Lorsqu’un visiteur effectue un achat (déclenche le `purchase` événement), cet accès et tous les accès suivants se déplacent dans la &quot;corbeille&quot; suivante. Par exemple, si un visiteur achète un produit de votre site pour la première fois, il passe de &quot;Pas un client&quot; à &quot;Nouveaux clients&quot;, la commande étant attribuée à &quot;Nouveaux clients&quot;. La valeur de dimension &quot;Pas un client&quot; ne peut pas être attribuée à des commandes.
