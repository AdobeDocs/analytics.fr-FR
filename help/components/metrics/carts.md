---
title: Paniers
description: Le nombre d’accès pendant lesquels un visiteur a ajouté son premier produit au panier.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
TQID: https://experienceleague.adobe.com/a-qT5Ly8-4mSBGbGTAzbwLIMRFZtqotMPvGFgOrM41Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 162
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
