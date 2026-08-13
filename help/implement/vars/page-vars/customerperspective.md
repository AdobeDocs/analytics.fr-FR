---
title: customerPerspective
description: Indique si un accès à l’application mobile s’est produit alors que l’application était en premier plan ou en arrière-plan.
feature: Appmeasurement Implementation
role: Admin, Developer
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 199
ht-degree: 0%

---

# customerPerspective

La variable `customerPerspective` spécifie si un accès à l’application mobile s’est produit alors que l’application était au premier plan ou en arrière-plan. Elle est envoyée à la collecte de données Adobe en tant que paramètre de requête `cp` et renseigne la dimension [Type d’accès](/help/components/dimensions/hit-type.md).

## Valeurs valides

`customerPerspective` accepte les valeurs de chaîne suivantes :

* `foreground` : l’accès s’est produit alors que l’application était en cours d’utilisation.
* `background` : l’accès s’est produit pendant l’exécution de l’application en arrière-plan, par exemple une mise à jour de l’emplacement ou un accès déclenché par une notification push.

## Définition de cette variable

Le SDK Mobile Adobe (version 4.13.6 et ultérieure) définit `customerPerspective` automatiquement ; vous ne le définissez généralement pas manuellement. Les accès envoyés depuis un navigateur via AppMeasurement sont toujours signalés comme `foreground`. Si la variable est absente d’un accès, cet accès est traité comme un accès de premier plan.

## Impact sur les rapports

La distinction entre premier plan et arrière-plan affecte le traitement des visites :

* Les visites ne sont comptabilisées que lorsqu’elles contiennent au moins un accès de premier plan.
* Les accès en arrière-plan peuvent toujours être attribués aux événements de conversion et peuvent être analysés par le biais de [sessions adaptées au contexte](/help/components/vrs/vrs-mobile-visit-processing.md) dans les suites de rapports virtuelles. Ce comportement est utile pour mesurer l’efficacité des notifications push.
