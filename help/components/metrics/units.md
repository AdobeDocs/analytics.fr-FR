---
title: Unités
description: Nombre total de produits achetés au cours de toutes les commandes.
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
TQID: https://experienceleague.adobe.com/0v4pF0Iv0IzU9K4CQiTy1-IIYgMCaO37E6QTmAAEPXc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 80%

---

# Unités

La [mesure](overview.md) « Unités » indique le nombre total de produits achetés dans toutes les commandes. Cette mesure est essentielle pour les sites d’e-commerce, car elle permet de mesurer la conversion. Vous pouvez combiner cette mesure avec n’importe quelle dimension pour déterminer les éléments de dimension ayant contribué au nombre de produits achetés. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension [Code de suivi](../dimensions/tracking-code.md)) ou les principaux termes de recherche interne (avec une [eVar](../dimensions/evar.md)) ayant contribué aux produits achetés.

## Méthode de calcul de cette mesure

Pour chaque accès où `purchase` figure dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md), additionnez le champ « Quantité » à la variable [`products`](/help/implement/vars/page-vars/products.md).

## Comparaison des commandes et des unités

La mesure [Commandes](orders.md) n’enregistre que le nombre d’événements d’achat. La mesure « Unités » est généralement supérieure à « Commandes », car les clients peuvent acheter plusieurs produits à la fois. Dans ce cas, une commande présente plusieurs unités.

Si les commandes sont supérieures aux unités, Adobe recommande de vérifier l’intégrité de votre mise en œuvre. Il est probable que votre variable `products` ne soit pas correctement définie pour les achats, ce qui n’est pas le comportement attendu.
