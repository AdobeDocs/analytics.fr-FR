---
title: Unités
description: Nombre total de produits achetés au cours de toutes les commandes.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---


# Unités

La mesure &quot;Unités&quot; indique le nombre total de produits achetés au cours de toutes les commandes. Cette mesure est essentielle pour les sites de commerce électronique pour mesurer la conversion. Vous pouvez associer cette mesure à n’importe quelle dimension pour identifier les éléments de dimension qui ont contribué au nombre de produits achetés. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension Code [de](../dimensions/tracking-code.md) suivi) ou les principaux termes de recherche interne (à l’aide d’une [eVar](../dimensions/evar.md)) qui ont contribué aux produits achetés.

## Méthode de calcul de cette mesure

Pour chaque accès où `purchase` se trouve la [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable, additionnez le champ &quot;Quantité&quot; dans la [`products`](/help/implement/vars/page-vars/products.md) variable.

## Comparaison des commandes et des unités

La mesure [Commandes](orders.md) n’enregistre que le nombre de événements d’achat. La mesure &quot;Unités&quot; est généralement supérieure à &quot;Commandes&quot;, car les clients peuvent acheter plusieurs produits. Dans ce cas, il existe une commande unique avec plusieurs unités.

Si les commandes sont supérieures aux unités, Adobe recommande de vérifier l’intégrité de votre mise en oeuvre. Il est probable que votre `products` variable ne soit pas correctement définie pour les achats, ce qui est généralement un comportement indésirable.
