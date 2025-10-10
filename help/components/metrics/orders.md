---
title: Commandes
description: Nombre d’achats effectués.
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
source-git-commit: a1fbd3f483d3a236fe5dc3246f5e90c1b3f51ba9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 65%

---

# Commandes

La mesure « Commandes »[&#128279;](overview.md) indique le nombre total d’événements d’achat effectués sur votre site. Cette mesure est essentielle pour les sites d’e-commerce, car elle permet de mesurer la conversion. Vous pouvez combiner cette mesure avec n’importe quelle dimension pour déterminer les éléments de dimension ayant contribué à une commande. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension [Code de suivi](../dimensions/tracking-code.md)) ou les principaux termes de recherche interne (avec [eVar](../dimensions/evar.md)) ayant contribué aux achats.

## Méthode de calcul de cette mesure

Cette mesure tient compte du nombre d’accès dans lesquels `purchase` se trouve dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).
