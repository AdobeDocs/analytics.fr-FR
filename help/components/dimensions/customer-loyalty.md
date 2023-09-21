---
title: Fidélité de la clientèle
description: Catégories basées sur le nombre d’achats précédents effectués par un visiteur.
feature: Dimensions
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 90%

---

# Fidélité de la clientèle

&quot;Fidélité de la clientèle&quot; [dimension](overview.md) indique le nombre de visiteurs de votre site qui ont effectué 0 achat précédent, 1 achat précédent, 2 achats précédents ou 3 achats précédents ou plus. Cette dimension est utile pour comprendre la façon dont votre site affecte le comportement d’achat. Vous pouvez également utiliser cette dimension dans un segment pour vous concentrer sur les visiteurs qui reviennent effectuer un achat, afin d’encourager un comportement similaire chez les nouveaux visiteurs.

## Renseignement de cette dimension avec des données

Adobe renseigne automatiquement cette dimension en fonction de l’événement [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) de votre mise en œuvre. Si vous implémentez l’événement `purchase` sur votre site, cette dimension fonctionne toujours.

## Éléments de dimension

Les éléments de dimension sont les suivants :

* **Pas un client** : au moment de l’accès, le visiteur n’a jamais effectué d’achat auparavant.
* **Nouveaux clients** : au moment de l’accès, le visiteur a effectué un seul achat auparavant.
* **Clients réguliers** : au moment de l’accès, le visiteur a effectué deux achats auparavant.
* **Clients fidèles** : au moment de l’accès, le visiteur a effectué trois achats ou plus auparavant.

Lorsqu’un visiteur effectue un achat (déclenche l’événement `purchase`), cet accès et tous les accès suivants passent dans le « regroupement » suivant. Par exemple, si un visiteur achète un produit de votre site pour la première fois, il passe de « Pas un client » à « Nouveaux clients », la commande étant attribuée à « Nouveaux clients ». Les commandes de l’élément de dimension « Pas un client » ne peuvent pas lui être attribuées.
