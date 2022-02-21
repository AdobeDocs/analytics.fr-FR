---
title: Unités
description: Nombre total de produits achetés au cours de toutes les commandes.
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 100%

---

# Unités

La mesure « Unités » indique le nombre total de produits achetés au cours de toutes les commandes. Cette mesure est essentielle pour les sites d’e-commerce, car elle permet de mesurer la conversion. Vous pouvez associer cette mesure à n’importe quelle dimension pour déterminer la contribution des éléments de dimension au nombre de produits achetés. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension [Code de suivi](../dimensions/tracking-code.md)) ou les principaux termes de recherche interne (avec une [eVar](../dimensions/evar.md)) ayant contribué aux produits achetés.

## Méthode de calcul de cette mesure

Pour chaque accès où `purchase` figure dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md), additionnez le champ « Quantité » à la variable [`products`](/help/implement/vars/page-vars/products.md).

## Comparaison des commandes et des unités

La mesure [Commandes](orders.md) n’enregistre que le nombre d’événements d’achat. La mesure « Unités » est généralement supérieure à « Commandes », car les clients peuvent acheter plusieurs produits à la fois. Dans ce cas, une commande présente plusieurs unités.

Si les commandes sont supérieures aux unités, Adobe recommande de vérifier l’intégrité de votre mise en œuvre. Il est probable que votre variable `products` ne soit pas correctement définie pour les achats, ce qui n’est pas le comportement attendu.
