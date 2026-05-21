---
title: Fidélité de la clientèle
description: Catégories basées sur le nombre d’achats précédents effectués par un visiteur.
feature: Dimensions
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
TQID: https://experienceleague.adobe.com/Essa0dflFlsqwtTQ4JdaSEOkX6T-zEYrQGhgXBWhfcI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 88%

---

# Fidélité de la clientèle

La [dimension](overview.md) « Fidélisation des clients » indique le nombre de visiteurs de votre site qui ont effectué 0 achat précédent, 1 achat précédent, 2 achats précédents ou plus de 3 achats précédents. Cette dimension est utile pour comprendre la façon dont votre site affecte le comportement d’achat. Vous pouvez également utiliser cette dimension dans un segment pour vous concentrer sur les visiteurs qui reviennent effectuer un achat, afin d’encourager un comportement similaire chez les nouveaux visiteurs.

## Renseignement de cette dimension avec des données

Adobe renseigne automatiquement cette dimension en fonction de l’événement [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) de votre mise en œuvre. Si vous implémentez l’événement `purchase` sur votre site, cette dimension fonctionne toujours.

## Éléments de dimension

Les éléments de dimension sont les suivants :

* **Pas un client** : au moment de l’accès, le visiteur n’a jamais effectué d’achat auparavant.
* **Nouveaux clients** : au moment de l’accès, le visiteur a effectué un seul achat auparavant.
* **Clients réguliers** : au moment de l’accès, le visiteur a effectué deux achats auparavant.
* **Clients fidèles** : au moment de l’accès, le visiteur a effectué trois achats ou plus auparavant.

Lorsqu’un visiteur effectue un achat (déclenche l’événement `purchase`), cet accès et tous les accès suivants passent dans le « regroupement » suivant. Par exemple, si un visiteur achète un produit de votre site pour la première fois, il passe de « Pas un client » à « Nouveaux clients », la commande étant attribuée à « Nouveaux clients ». Les commandes de l’élément de dimension « Pas un client » ne peuvent pas lui être attribuées.
